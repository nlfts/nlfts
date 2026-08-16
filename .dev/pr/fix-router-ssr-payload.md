# fix(router,ssr): 修复 Vue Router 警告、SSR 渲染崩溃及博客文件命名问题

---

## 提交标题

```
fix(router,ssr,content): 修复社交媒体跳转路由警告、SSR payload 渲染崩溃及博客内容文件命名规范
```

---

## 变更概览

本次 PR 修复了三个相互关联的问题，这些问题在滚动首页时通过浏览器控制台暴露出来。

---

## 问题一 — Vue Router 警告：找不到路径匹配

**受影响文件：** `app/components/AppFooter.vue`

**根本原因：**
`/instagram`、`/tiktok`、`/linkedin`、`/wa`、`/discord`、`/partner` 等路径实际上是
Nitro 服务端路由（`server/routes/*.ts`），负责执行 302 跳转至外部 URL。
然而页脚使用了 `<NuxtLink>` 来渲染这些链接，导致 Vue Router 在客户端尝试解析
这些路径时找不到对应的 SPA 路由，并抛出警告。

此外，页脚链接 `Mitra` 指向 `/partners`（复数），而实际服务端路由文件为
`partner.ts`（对应 `/partner`），导致 404。

**修复内容：**
- 新增 `SERVER_ROUTES` Set，包含所有由 Nitro 处理的服务端跳转路径
- 新增 `isServerRoute()` 辅助函数
- 页脚列链接改为条件渲染：服务端路由或外部链接使用 `<a>`，内部页面保留 `<NuxtLink>`
- 社交媒体图标链接从 `<NuxtLink>` 改为 `<a>`，并补充 `rel="noopener noreferrer"`
- 将 `Mitra` 链接从 `/partners` 修正为 `/partner`

---

## 问题二 — SSR Payload 500：渲染处理器无响应

**受影响文件：** `app/components/DevSection.vue`、`app/components/BlogSection.vue`

**根本原因：**
`DevSection.vue` 在 `<script setup>` 顶层直接调用了 `gsap.registerPlugin(ScrollTrigger)`，
没有 `process.client` 守卫。`ScrollTrigger` 在注册时会访问 `window` 和 `document`，
而这些对象在 Node.js 服务端环境中不存在，导致 Nitro 渲染处理器抛出未捕获异常，
无法返回响应，从而引发 `/_payload.json` 和 `/blog/_payload.json` 的 500 错误。

`BlogSection.vue` 存在另一个问题：`onUnmounted` 被嵌套在 `onMounted` 回调内部调用。
由于 `await useAsyncData()` 之后 Vue 的组件上下文已经失效，该生命周期钩子无法
正确关联到当前组件，导致控制台警告。

**修复内容：**

`DevSection.vue`：
- 将 `gsap.registerPlugin(ScrollTrigger)` 移入 `if (process.client)` 守卫块
- 删除顶层的重复 `gsap.registerPlugin(ScrollTrigger)` 调用

`BlogSection.vue`：
- 将 `ctx` 变量提升至 `setup()` 作用域（`let ctx: gsap.Context | null = null`）
- 将 `onUnmounted(() => ctx?.revert())` 移至 `setup()` 顶层，不再嵌套于 `onMounted` 内

---

## 问题三 — 博客内容文件命名不规范

**受影响文件：** `content/3.blog/` 目录下三个 Markdown 文件

**根本原因：**
博客文章文件名包含空格，`@nuxt/content` v3 在索引内容时无法正确处理，
导致 `queryCollection('posts')` 失败，间接加重了 SSR 崩溃问题。
其中一个文件还缺少数字前缀后的点号分隔符（`1TypeScript...` 而非 `1.TypeScript...`）。

**修复内容：**
- `1TypeScript-...md` → `1.TypeScript-...md`（补充点号分隔符）
- `2.Nuxt 4 Antara...md` → `2.Nuxt-4-Antara-...md`（空格替换为连字符）
- `6.JavaScript Modern Stack...md` → `6.JavaScript-Modern-Stack-...md`（同上）

---

## 变更文件列表

| 文件 | 变更类型 | 说明 |
|------|----------|------|
| `app/components/AppFooter.vue` | 修改 | 修复路由警告，区分服务端路由与内部页面链接 |
| `app/components/DevSection.vue` | 修改 | 添加 `process.client` 守卫，修复 SSR 崩溃 |
| `app/components/BlogSection.vue` | 修改 | 修复 `onUnmounted` 生命周期注入位置错误 |
| `content/3.blog/1.TypeScript-...md` | 重命名 | 修正文件命名（补充点号） |
| `content/3.blog/2.Nuxt-4-Antara-...md` | 重命名 | 修正文件命名（空格→连字符） |
| `content/3.blog/6.JavaScript-Modern-Stack-...md` | 重命名 | 修正文件命名（空格→连字符） |

---

## 测试说明

- 首页滚动不再出现 `[Vue Router warn]: No match found` 警告
- `/_payload.json` 与 `/blog/_payload.json` 不再返回 500
- `BlogSection.vue` 不再出现 `onUnmounted` 生命周期警告
- 所有博客文章可通过 `queryCollection('posts')` 正常查询
- 社交媒体链接点击后正常跳转（通过 Nitro 302 重定向至外部 URL）

---

> 📝 本文档由 Kiro 自动生成 · 语言：中文（简体）· 格式：Conventional Commits
