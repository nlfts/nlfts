<script setup lang="ts">
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

if (process.client) {
  gsap.registerPlugin(ScrollTrigger)
}

const sectionRef = ref<HTMLElement | null>(null)

const { data: posts } = await useAsyncData('latest-posts', () =>
  queryCollection('posts')
    .order('date', 'DESC')
    .limit(3)
    .all()
)

// ctx harus dideklarasikan di scope setup() agar onUnmounted bisa mengaksesnya
let ctx: gsap.Context | null = null

onMounted(async () => {
  await nextTick()
  if (!sectionRef.value) return

  ctx = gsap.context(() => {
    gsap.from(".blog-reveal", {
      scrollTrigger: {
        trigger: sectionRef.value,
        start: "top 85%",
        toggleActions: "play none none reverse"
      },
      y: 30,
      opacity: 0,
      duration: 1,
      stagger: 0.15,
      ease: "power2.out"
    })
  }, sectionRef.value)
})

// onUnmounted harus di scope setup() langsung, bukan di dalam onMounted
onUnmounted(() => {
  ctx?.revert()
})
</script>

<template>
  <section 
  ref="sectionRef"
  class="py-32 bg-white dark:bg-[#09090b] text-zinc-900 dark:text-zinc-100"
>
  <UContainer>
    <div class="mb-20">
      <h2 class="text-sm font-medium tracking-tight mb-2 opacity-60">Pikiran & Catatan</h2>
      <div class="flex items-center justify-between">
        <h3 class="text-5xl font-light tracking-tighter">Artikel Terbaru</h3>
        <NuxtLink to="/blog" class="text-sm border-b border-zinc-300 dark:border-zinc-700 hover:border-zinc-900 dark:hover:border-zinc-100 transition-colors">
          Lihat Semua
        </NuxtLink>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-0 border-t border-l border-zinc-200 dark:border-zinc-800">
    <div 
        v-for="(post, index) in posts" 
        :key="index"
        class="blog-reveal border-r border-b border-zinc-200 dark:border-zinc-800 p-8 hover:bg-zinc-50 dark:hover:bg-zinc-900/50 transition-colors group"
      >
        <NuxtLink :to="post.path" class="flex flex-col h-full justify-between">
          <div class="space-y-6">
            <span class="block text-[11px] uppercase tracking-[0.2em] opacity-50">
              {{ new Date(post.date).toLocaleDateString('id-ID', { month: 'long', day: 'numeric' }) }}
            </span>
            
            <h4 class="text-xl font-medium leading-snug group-hover:opacity-70 transition-opacity">
              {{ post.title }}
            </h4>
            
            <p class="text-sm text-zinc-500 leading-relaxed font-light">
              {{ post.description }}
            </p>
          </div>

          <div class="mt-8 flex items-center text-[10px] font-bold uppercase tracking-widest opacity-30 group-hover:opacity-100 transition-opacity">
            Baca Selengkapnya ↗
          </div>
        </NuxtLink>
      </div>
    </div>
  </UContainer>
</section>
</template>

<style scoped>
section {
  font-feature-settings: \"cv11\", \"ss01\", \"cv01\";
}
</style>
