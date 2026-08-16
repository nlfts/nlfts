<script setup>
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

if (process.client) {
  gsap.registerPlugin(ScrollTrigger)
}

// Dummy Data Kontributor
const contributors = [
  { name: 'Kin You', avatar: 'https://avatars.githubusercontent.com/u/228851591?v=4' },
  { name: 'Nairha', avatar: 'https://avatars.githubusercontent.com/u/204519754?s=130&v=4' },
  { name: 'Cery', avatar: 'https://avatars.githubusercontent.com/u/190081649?s=130&v=4' },
  { name: 'yanfe1', avatar: 'https://avatars.githubusercontent.com/u/238488059?s=130&v=4' },
  { name: 'Mugi', avatar: 'https://avatars.githubusercontent.com/u/289261759?s=130&v=4' },
  { name: 'titu', avatar: 'https://avatars.githubusercontent.com/u/222330932?s=130&v=4' },
  { name: 'xianzink', avatar: 'https://avatars.githubusercontent.com/u/284604593?s=130&v=4' },
  { name: 'fandy', avatar: 'https://avatars.githubusercontent.com/u/216720543?s=130&v=4' },
  { name: 'Ajrin', avatar: 'https://github.com/BeedBest.png' },
  { name: 'Guh', avatar: 'https://avatars.githubusercontent.com/u/228839856?s=130&v=4' },
  { name: 'Ahmad', avatar: 'https://avatars.githubusercontent.com/u/225441519?s=130&v=4' },
  { name: 'Rehan', avatar: 'https://avatars.githubusercontent.com/u/218329504?s=130&v=4' },
  { name: 'Habsy', avatar: 'https://github.com/clarkaiden.png' },
  { name: 'Vahlzzz', avatar: 'https://avatars.githubusercontent.com/u/202130049?s=130&v=4' },
  { name: 'Nif', avatar: 'https://avatars.githubusercontent.com/u/232500114?s=130&v=4' },
  { name: 'dikqst', avatar: 'https://avatars.githubusercontent.com/u/230048582?s=130&v=4' },
  { name: 'Xiaomei', avatar: 'https://avatars.githubusercontent.com/u/228843429?s=130&v=4' },
  { name: 'Destkaa', avatar: 'https://avatars.githubusercontent.com/u/228332586?s=130&v=4' },
  { name: 'Radiet', avatar: 'https://avatars.githubusercontent.com/u/226198461?s=130&v=4' },
  { name: 'Fakhri', avatar: 'https://avatars.githubusercontent.com/u/228840381?s=130&v=4' },
  { name: 'Ilaman', avatar: 'https://avatars.githubusercontent.com/u/228839961?s=130&v=4' },
  { name: 'jauf', avatar: 'https://avatars.githubusercontent.com/u/167701174?s=130&v=4' },
  { name: 'ferrr', avatar: 'https://avatars.githubusercontent.com/u/234127916?s=130&v=4' },
  { name: 'Naffez', avatar: 'https://avatars.githubusercontent.com/u/182593937?v=4' }
]

onMounted(() => {
  gsap.fromTo('.contributor-item', 
    { opacity: 0, scale: 0.8 },
    { 
      opacity: 1, 
      scale: 1, 
      duration: 0.6, 
      stagger: 0.03, 
      scrollTrigger: {
        trigger: '.contributor-grid',
        start: 'top 80%'
      }
    }
  )
})
</script>


<template>
  <section class="py-24 bg-white dark:bg-[#09090b] transition-colors duration-300 overflow-hidden">
    <UContainer>
      <div class="flex flex-col lg:flex-row items-center gap-16">
        
        <div class="contributor-grid grid grid-cols-6 sm:grid-cols-8 lg:grid-cols-6 gap-3 lg:gap-4 max-w-2xl">
          <div 
            v-for="(person, index) in contributors" 
            :key="index"
            class="contributor-item aspect-square rounded-xl overflow-hidden border border-zinc-200 dark:border-white/5 hover:border-zinc-400 dark:hover:border-white/20 transition-colors bg-zinc-100 dark:bg-white/5"
          >
            <img 
              :src="person.avatar" 
              :alt="person.name" 
              class="w-full h-full object-cover"
              width="64"
              height="64"
              loading="lazy"
            />
          </div>
        </div>

        <div class="flex-1 space-y-6">
          <h2 class="group text-4xl md:text-5xl font-bold tracking-tight text-zinc-900 dark:text-white">
            Dibangun oleh 
            <span class="transition-colors duration-300">
              <span class="group-hover:hidden">developer</span>
              
              <span class="hidden group-hover:inline">
                Dev<span class="text-pink-500">lovers</span>
              </span>
            </span> 
            di seluruh Indonesia.
          </h2>
          <p class="text-zinc-600 dark:text-zinc-400 text-lg">
            Ratusan kontributor membuat NLFTs lebih baik setiap hari. Bergabunglah dengan kami dan bangun masa depan web yang terbuka.
          </p>
          
          <div class="flex items-center gap-4 pt-4">
            <UButton 
              label="Develovers" 
              icon="i-heroicons-user-group" 
              variant="solid" 
              color="black"
              @click="$router.push('/halaman-tujuan')"
              class="cursor-pointer"
            />
            <div class="flex gap-4 text-zinc-500 dark:text-zinc-400">
              <UIcon name="i-simple-icons-discord" class="w-6 h-6 hover:text-zinc-900 dark:hover:text-white cursor-pointer transition-colors" />
              <UIcon name="i-simple-icons-x" class="w-6 h-6 hover:text-zinc-900 dark:hover:text-white cursor-pointer transition-colors" />
              <UIcon name="i-simple-icons-bluesky" class="w-6 h-6 hover:text-zinc-900 dark:hover:text-white cursor-pointer transition-colors" />
            </div>
          </div>
        </div>

      </div>
    </UContainer>
  </section>
</template>