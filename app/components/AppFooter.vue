<script setup lang="ts">
import gsap from 'gsap'


// Routes yang ditangani oleh Nitro server route (bukan halaman Vue/SPA)
// Harus menggunakan <a> biasa agar tidak di-prefetch oleh Vue Router
const SERVER_ROUTES = new Set(['/partner', '/discord', '/wa', '/instagram', '/tiktok', '/linkedin', '/x', '/bsky', '/community', '/sponsor', '/marketplace', '/huggingface', '/kontak'])

const isServerRoute = (path: string) => SERVER_ROUTES.has(path)

const columns = [
  {
    label: 'Product',
    children: [
      { label: 'Education', to: 'https://edu.nlfts.dev' },
      { label: 'FTs DevTools', to: 'https://github.com/Vuxilabs/fts-devtools' },
      { label: 'Travellings.id', to: 'https://tv.nlfts.dev' },
      { label: 'Lions Pos', to: 'https://github.com/nlfts/Lions-Pos' }
    ]
  },
  {
    label: 'Partner',
    children: [
      { label: 'Grantara Indonesia', to: 'https://grabals-official.vercel.app/' },
      { label: 'Vuxilabs', to: 'https://github.com/vuxilabs' },
      { label: 'Rakitweb Solution', to: 'https://rakitweb.site' },
      { label: 'Storia Market Place', to: 'https://storia-market.vercel.app' }
    ]
  },
  {
    label: 'Perusahaan',
    children: [
      { label: 'Tentang', to: '/about' },
      { label: 'Karir', to: '/karir' },
      { label: 'Terhubung', to: '/terhubung' },
      { label: 'DevLovers', to: '/members' },
      { label: 'Blog', to: '/blog' },
      { label: 'Sponsors', to: 'https://github.com/sponsors/NLFTs' },
      { label: 'Kontak', to: '/contact' },
      { label: 'Mitra', to: '/partner' },
      { label: 'Donasi', to: '/donasi' },
      { label: 'Meet', to: 'https://cal.com/nlfts' }
    ]
  },
  {
    label: 'Legal',
    children: [
      { label: 'Kebijakan Privasi', to: '/docs/legal/privacy' },
      { label: 'Syarat & Ketentuan', to: '/docs/legal/tos' },
      { label: 'Kebijakan Anti-Bullying', to: '/docs/legal/anti-bully' },
      { label: 'FAQ', to: '/faq' },
      { label: 'Dukungan 24/7', to: '/discord' }
    ]
  }
]

const socialLinks = [
  { icon: 'i-simple-icons-github', to: 'https://github.com/NLFTs', label: 'GitHub' },
  { icon: 'i-simple-icons-instagram', to: '/instagram', label: 'Instagram' },
  { icon: 'i-simple-icons-whatsapp', to: '/wa', label: 'WhatsApp' },
  { icon: 'i-simple-icons-tiktok', to: '/tiktok', label: 'TikTok' },
  { icon: 'i-simple-icons-linkedin', to: '/linkedin', label: 'LinkedIn' },
  { icon: 'i-simple-icons-discord', to: '/discord', label: 'Discord' }
]

// Elite Magnetic Link Effect
const onLinkEnter = (e: MouseEvent) => {
  const el = e.currentTarget as HTMLElement
  const underline = el.querySelector(".link-line")
  const aura = el.querySelector(".link-aura")
  
  gsap.to(el, {
    x: 8,
    scale: 1.05,
    color: '#10B981',
    duration: 0.5,
    ease: "elastic.out(1, 0.5)"
  })

  if (underline) {
    gsap.to(underline, {
      scaleX: 1,
      opacity: 1,
      duration: 0.6,
      ease: "power4.out"
    })
  }

  if (aura) {
    gsap.to(aura, {
      opacity: 0.1,
      scale: 1,
      duration: 0.4
    })
  }
}

const onLinkLeave = (e: MouseEvent) => {
  const el = e.currentTarget as HTMLElement
  const underline = el.querySelector(".link-line")
  const aura = el.querySelector(".link-aura")

  gsap.to(el, {
    x: 0,
    scale: 1,
    color: '#6B7280',
    duration: 0.8,
    ease: "elastic.out(1, 0.3)"
  })

  if (underline) {
    gsap.to(underline, {
      scaleX: 0,
      opacity: 0,
      duration: 0.4
    })
  }

  if (aura) {
    gsap.to(aura, {
      opacity: 0,
      scale: 0.5,
      duration: 0.4
    })
  }
}

// Magnetic Social Pull
const onSocialMove = (e: MouseEvent) => {
  const el = e.currentTarget as HTMLElement
  const rect = el.getBoundingClientRect()
  const mouseX = e.clientX - rect.left - rect.width / 2
  const mouseY = e.clientY - rect.top - rect.height / 2
  
  gsap.to(el, {
    x: mouseX * 0.4,
    y: mouseY * 0.4,
    scale: 1.2,
    color: '#10B981',
    duration: 0.3,
    ease: "power2.out"
  })
}

const onSocialLeave = (e: MouseEvent) => {
  gsap.to(e.currentTarget, {
    x: 0,
    y: 0,
    scale: 1,
    color: '#9CA3AF',
    duration: 0.6,
    ease: "elastic.out(1, 0.3)"
  })
}


</script>

<template>
  <footer
    class="relative bg-white dark:bg-[#09090b] pt-24 overflow-hidden border-t border-zinc-200/80 dark:border-zinc-800"
  >
    <UContainer class="pb-[380px] lg:pb-[480px]">
      <!-- TOP GRID -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-24">

        <!-- BRANDING & UTILITY -->
        <div class="lg:col-span-4 flex flex-col justify-between">
          <div class="space-y-6">
            <span class="text-xl font-bold tracking-tighter text-gray-900 dark:text-white">NLFT<span class="text-primary-500">s</span></span>
            <p class="text-sm text-gray-500 dark:text-gray-400 max-w-[240px] leading-relaxed">
              Membangun masa depan perangkat lunak melalui kolaborasi komunitas.
            </p>
          </div>

          <div class="mt-8 lg:mt-0 text-[10px] uppercase tracking-widest text-gray-400">
            &copy; {{ new Date().getFullYear() }} NLFTs. All rights reserved.
          </div>
        </div>

        <!-- LINKS -->
        <div class="lg:col-span-8 grid grid-cols-2 md:grid-cols-4 gap-8">
          <div v-for="col in columns" :key="col.label" class="space-y-6">
            <h3 class="text-[10px] font-bold uppercase tracking-widest text-gray-900 dark:text-white">
              {{ col.label }}
            </h3>
            <ul class="space-y-3">
              <li v-for="link in col.children" :key="link.label">
                <!-- Gunakan <a> untuk external URL dan server routes (agar tidak di-prefetch Vue Router) -->
                <a
                  v-if="link.to.startsWith('http') || isServerRoute(link.to)"
                  :href="link.to"
                  :target="link.to.startsWith('http') ? '_blank' : undefined"
                  :rel="link.to.startsWith('http') ? 'noopener noreferrer' : undefined"
                  class="text-sm text-gray-500 hover:text-primary-500 dark:text-gray-400 transition-colors duration-200"
                >
                  {{ link.label }}
                </a>
                <NuxtLink
                  v-else
                  :to="link.to"
                  class="text-sm text-gray-500 hover:text-primary-500 dark:text-gray-400 transition-colors duration-200"
                >
                  {{ link.label }}
                </NuxtLink>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <!-- SOCIALS BOTTOM BAR -->
      <div class="mt-24 flex items-center justify-between border-t border-gray-100 dark:border-gray-800 pt-8">
        <div class="flex items-center gap-6">
          <a
            v-for="social in socialLinks"
            :key="social.label"
            :href="social.to"
            target="_blank"
            rel="noopener noreferrer"
            :aria-label="social.label"
            class="text-gray-400 hover:text-gray-900 dark:hover:text-white transition-colors"
          >
            <UIcon :name="social.icon" class="w-5 h-5" />
          </a>
        </div>

        <div class="flex gap-6 text-[11px] font-medium text-gray-400">
          <!-- Removed broken internal links to avoid prerendering 404 routes -->
        </div>
      </div>
    </UContainer>

    <!-- GIANT BRANDING TEXT — menempel persis di bawah footer -->
    <div
      class="absolute bottom-0 left-0 right-0 select-none pointer-events-none overflow-hidden"
      aria-hidden="true"
    >
      <h1
        class="giant-branding w-full text-center text-[clamp(180px,25vw,520px)] max-lg:text-[clamp(120px,18vw,520px)] font-[1000] leading-none tracking-[-0.08em] whitespace-nowrap"
        style="transform: translateY(28%);"
      >
        <span class="text-zinc-900 dark:text-white">NLFT</span><span class="text-primary-500">s</span>
      </h1>

      <!-- Efek tenggelam ke kegelapan / darkness -->
      <div
        class="absolute inset-x-0 bottom-0 h-[60%] bg-gradient-to-t from-white dark:from-[#09090b] via-white/80 dark:via-[#09090b]/80 to-transparent pointer-events-none"
      />
    </div>
  </footer>
</template>

<style scoped>
footer {
  font-feature-settings: "cv11", "ss01", "cv01";
}
</style>
