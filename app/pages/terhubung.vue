<template>
  <div class="min-h-screen bg-white dark:bg-[#09090b] text-zinc-900 dark:text-zinc-100 transition-colors duration-300">
      <header
    ref="headerRef"
    class="relative px-6 py-16 md:py-24 lg:py-32 text-center max-w-4xl mx-auto space-y-6 md:space-y-8 overflow-hidden"
    @mousemove="onMouseMove"
  >
    <!-- Glow yang mengikuti kursor -->
    <div
      ref="glowRef"
      class="pointer-events-none absolute w-[500px] h-[500px] rounded-full bg-gradient-to-br from-indigo-400/20 via-fuchsia-300/10 to-transparent blur-3xl -z-10"
      style="top: -250px; left: -250px;"
    />

    <!-- Garis aksen kecil yang menggambar dari 0 -> full -->
    <div class="flex justify-center">
      <span ref="lineRef" class="block h-[2px] w-0 bg-zinc-950 dark:bg-white origin-left" />
    </div>

    <h1
      ref="titleRef"
      class="text-4xl md:text-5xl lg:text-7xl font-light tracking-tight text-zinc-950 dark:text-white leading-tight"
    >
      Mari membangun ekosistem digital bersama.
    </h1>

    <p
      ref="subRef"
      class="text-lg md:text-xl text-zinc-600 dark:text-zinc-400 font-light opacity-0"
    >
      Konektivitas adalah fondasi dari inovasi. Pilih cara terbaik untuk terhubung dengan komunitas dan tim pengembang kami.
    </p>
  </header>

    <!-- Section Discord -->
  <section class="bg-zinc-50 dark:bg-[#09090b] py-16 md:py-24 lg:py-32 text-zinc-900 dark:text-white transition-colors duration-300">
    <div class="mx-auto max-w-7xl px-4 md:px-6">
      <div class="grid items-center gap-10 lg:gap-20 lg:grid-cols-[480px_1fr]">
 
        <!-- LEFT -->
        <div class="max-w-lg">
          <span class="mb-6 inline-flex rounded-full border border-zinc-200 dark:border-zinc-800 px-4 py-1 text-xs tracking-[0.2em] uppercase text-zinc-500">
            Community
          </span>
          <h2 class="text-4xl font-semibold leading-tight tracking-tight md:text-5xl text-zinc-950 dark:text-white">
            Gabung Dengan
            <span class="text-[#5865F2]">Discord</span>
          </h2>
          <p class="mt-8 text-base leading-8 text-zinc-600 dark:text-zinc-400">
            Bergabung bersama komunitas kami untuk berdiskusi,
            mendapatkan update terbaru, berbagi karya, dan
            berinteraksi dengan anggota lain kapan saja.
          </p>
          <div class="mt-8 md:mt-10 flex flex-wrap gap-3 md:gap-4">
            <NuxtLink
              to="/discord"
              external
              target="_blank"
              class="cursor-pointer inline-flex rounded-xl bg-zinc-900 dark:bg-white px-7 py-3 text-sm font-medium text-black dark:text-black transition hover:opacity-90 shadow-sm"
            >
              Masuk Discord
            </NuxtLink>
            <NuxtLink
              to="/docs/getting-started#discord"
              class="rounded-xl border border-zinc-300 dark:border-zinc-800 px-7 py-3 text-sm font-medium text-zinc-700 dark:text-zinc-300 transition hover:bg-zinc-100 dark:hover:bg-zinc-900/50 hover:border-zinc-400 dark:hover:border-zinc-700"
            >
              Pelajari Lebih Lanjut
            </NuxtLink>
          </div>
        </div>
 
        <!-- RIGHT: Discord Window -->
        <div class="relative">
          <div class="absolute inset-0 -z-10 blur-3xl opacity-20 bg-[#5865F2]" />
 
          <div class="overflow-hidden rounded-2xl border border-zinc-800 bg-[#0d0d10] shadow-[0_40px_100px_rgba(0,0,0,0.5)] w-full">
 
            <!-- Mac Header -->
            <div class="flex items-center gap-2 border-b border-zinc-800 px-5 py-4">
              <span class="h-3 w-3 rounded-full bg-red-500" />
              <span class="h-3 w-3 rounded-full bg-yellow-500" />
              <span class="h-3 w-3 rounded-full bg-green-500" />
              <div class="ml-auto text-xs text-zinc-500">NLFTs C-OSS</div>
            </div>
 
            <!-- Discord Body -->
            <div class="flex h-[340px] sm:h-[380px] md:h-[420px]">
 
              <!-- Server Icons Sidebar -->
              <div class="hidden sm:flex w-[68px] border-r border-zinc-800 bg-[#09090b] flex-col items-center gap-3 py-4">
                <div class="relative">
                  <div class="h-12 w-12 rounded-2xl bg-[#5865F2] flex items-center justify-center text-white font-bold text-lg cursor-pointer">
                    F
                  </div>
                  <div class="absolute left-0 top-1/2 -translate-y-1/2 -translate-x-1 w-1 h-8 bg-white rounded-r-full" />
                </div>
                <div class="w-8 h-px bg-zinc-800" />
                <div class="h-12 w-12 rounded-full bg-zinc-800 flex items-center justify-center text-zinc-400 text-xs cursor-pointer hover:rounded-2xl hover:bg-[#5865F2] hover:text-white transition-all duration-200">G</div>
                <div class="h-12 w-12 rounded-full bg-zinc-800 flex items-center justify-center text-zinc-400 text-xs cursor-pointer hover:rounded-2xl hover:bg-green-600 hover:text-white transition-all duration-200">N</div>
                <div class="h-12 w-12 rounded-full bg-zinc-800 flex items-center justify-center text-green-400 text-xl cursor-pointer hover:rounded-2xl hover:bg-green-600 hover:text-white transition-all duration-200">+</div>
              </div>
 
              <!-- Channel List -->
              <div class="hidden md:flex w-[200px] border-r border-zinc-800 bg-[#111214] flex-col">
                <div class="flex items-center justify-between px-4 py-3 border-b border-zinc-800 cursor-pointer hover:bg-zinc-800/50 transition">
                  <h3 class="text-sm font-semibold text-white truncate">NLFTs C-OSS</h3>
                  <svg class="w-4 h-4 text-zinc-400 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
                  </svg>
                </div>
 
                <div class="flex-1 overflow-y-auto py-3 px-2 space-y-4 scrollbar-none">
                  <!-- Information -->
                  <div>
                    <button class="flex items-center gap-1 w-full px-1 mb-1" @click="toggleCategory('info')">
                      <svg class="w-2.5 h-2.5 text-zinc-500 transition-transform" :class="categories.info ? '' : '-rotate-90'" fill="currentColor" viewBox="0 0 24 24"><path d="M7 10l5 5 5-5z"/></svg>
                      <span class="text-[10px] uppercase tracking-wider text-zinc-500 font-semibold">Information</span>
                    </button>
                    <div v-if="categories.info">
                      <button
                        @click="activeChannel = 'papan-info'"
                        :class="['flex items-center gap-2 w-full rounded-md px-2 py-1.5 text-xs transition-colors', activeChannel === 'papan-info' ? 'bg-zinc-700/60 text-white' : 'text-zinc-400 hover:bg-zinc-800/60 hover:text-zinc-300']"
                      >
                        <span class="text-zinc-500 font-medium">#</span>
                        papan-info
                        <span v-if="activeChannel === 'papan-info'" class="ml-auto w-1.5 h-1.5 rounded-full bg-white" />
                      </button>
                    </div>
                  </div>
 
                  <!-- Text Channels -->
                  <div>
                    <button class="flex items-center gap-1 w-full px-1 mb-1" @click="toggleCategory('text')">
                      <svg class="w-2.5 h-2.5 text-zinc-500 transition-transform" :class="categories.text ? '' : '-rotate-90'" fill="currentColor" viewBox="0 0 24 24"><path d="M7 10l5 5 5-5z"/></svg>
                      <span class="text-[10px] uppercase tracking-wider text-zinc-500 font-semibold">Text Channels</span>
                    </button>
                    <div v-if="categories.text">
                      <button
                        @click="activeChannel = 'lobby'"
                        :class="['flex items-center gap-2 w-full rounded-md px-2 py-1.5 text-xs transition-colors', activeChannel === 'lobby' ? 'bg-zinc-700/60 text-white' : 'text-zinc-400 hover:bg-zinc-800/60 hover:text-zinc-300']"
                      >
                        <span class="text-zinc-500 font-medium">#</span>
                        lobby
                        <span class="ml-auto bg-[#5865F2] text-white text-[9px] rounded-full w-4 h-4 flex items-center justify-center font-semibold">4</span>
                      </button>
                    </div>
                  </div>
 
                  <!-- Voice Channels -->
                  <div>
                    <button class="flex items-center gap-1 w-full px-1 mb-1" @click="toggleCategory('voice')">
                      <svg class="w-2.5 h-2.5 text-zinc-500 transition-transform" :class="categories.voice ? '' : '-rotate-90'" fill="currentColor" viewBox="0 0 24 24"><path d="M7 10l5 5 5-5z"/></svg>
                      <span class="text-[10px] uppercase tracking-wider text-zinc-500 font-semibold">Voice Channels</span>
                    </button>
                    <div v-if="categories.voice" class="space-y-0.5">
                      <button
                        @click="activeChannel = 'voice-24jam'"
                        :class="['flex items-center gap-1.5 w-full rounded-md px-2 py-1.5 text-xs transition-colors', activeChannel === 'voice-24jam' ? 'bg-zinc-700/60 text-white' : 'text-zinc-400 hover:bg-zinc-800/60 hover:text-zinc-300']"
                      >
                        <svg class="w-3.5 h-3.5 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3a3 3 0 0 0-3 3v6a3 3 0 0 0 6 0V6a3 3 0 0 0-3-3zm-1 13.93V19H9v2h6v-2h-2v-2.07A7.003 7.003 0 0 0 19 10h-2a5 5 0 0 1-10 0H5a7.003 7.003 0 0 0 6 6.93z"/></svg>
                        <span class="truncate">24-jam Non Stop</span>
                      </button>
                      <button
                        @click="activeChannel = 'voice-vuxilabs'"
                        :class="['flex items-center gap-1.5 w-full rounded-md px-2 py-1.5 text-xs transition-colors', activeChannel === 'voice-vuxilabs' ? 'bg-zinc-700/60 text-white' : 'text-zinc-400 hover:bg-zinc-800/60 hover:text-zinc-300']"
                      >
                        <svg class="w-3.5 h-3.5 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3a3 3 0 0 0-3 3v6a3 3 0 0 0 6 0V6a3 3 0 0 0-3-3zm-1 13.93V19H9v2h6v-2h-2v-2.07A7.003 7.003 0 0 0 19 10h-2a5 5 0 0 1-10 0H5a7.003 7.003 0 0 0 6 6.93z"/></svg>
                        vuxilabs
                      </button>
                    </div>
                  </div>
                </div>
 
                <!-- User bar -->
                <div class="border-t border-zinc-800 px-2 py-2 flex items-center gap-2 bg-[#0e0e10]">
                  <div class="relative">
                    <div class="w-7 h-7 rounded-full bg-[#5865F2] flex items-center justify-center text-white text-xs font-semibold">Y</div>
                    <div class="absolute -bottom-0.5 -right-0.5 w-2.5 h-2.5 rounded-full bg-green-500 border-2 border-[#0e0e10]" />
                  </div>
                  <div class="flex-1 min-w-0">
                    <p class="text-xs font-medium text-white truncate leading-none">you</p>
                    <p class="text-[9px] text-zinc-500 truncate">#0001</p>
                  </div>
                </div>
              </div>
 
              <!-- Main Content -->
              <div class="flex-1 bg-[#141518] flex flex-col overflow-hidden min-w-0">
 
                <!-- Channel Header -->
                <div class="flex items-center gap-2 px-3 py-2.5 border-b border-zinc-800 flex-shrink-0">
                  <template v-if="activeChannel === 'papan-info'">
                    <span class="text-zinc-400 font-medium">#</span>
                    <span class="text-xs font-semibold text-white">papan-info</span>
                    <div class="w-px h-3 bg-zinc-700 mx-1" />
                    <span class="text-[10px] text-zinc-500 truncate">Informasi resmi server</span>
                  </template>
                  <template v-else-if="activeChannel === 'lobby'">
                    <span class="text-zinc-400 font-medium">#</span>
                    <span class="text-xs font-semibold text-white">lobby</span>
                    <div class="w-px h-3 bg-zinc-700 mx-1" />
                    <span class="text-[10px] text-zinc-500 truncate">Ngobrol santai</span>
                  </template>
                  <template v-else>
                    <svg class="w-4 h-4 text-zinc-400 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3a3 3 0 0 0-3 3v6a3 3 0 0 0 6 0V6a3 3 0 0 0-3-3zm-1 13.93V19H9v2h6v-2h-2v-2.07A7.003 7.003 0 0 0 19 10h-2a5 5 0 0 1-10 0H5a7.003 7.003 0 0 0 6 6.93z"/></svg>
                    <span class="text-xs font-semibold text-white truncate">
                      {{ activeChannel === 'voice-24jam' ? '24-jam Non Stop' : 'vuxilabs' }}
                    </span>
                  </template>
                  <div class="ml-auto flex-shrink-0">
                    <button class="p-1 rounded hover:bg-zinc-700 text-zinc-500 hover:text-white transition">
                      <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/></svg>
                    </button>
                  </div>
                </div>
 
                <!-- Scrollable Chat -->
                <div class="flex-1 overflow-y-auto p-3 space-y-3 scrollbar-none">
 
                  <!-- #papan-info -->
                  <template v-if="activeChannel === 'papan-info'">
                    <div class="flex justify-center mb-3">
                      <span class="text-[10px] text-zinc-500 bg-zinc-800/50 rounded-full px-3 py-1">Awal dari #papan-info</span>
                    </div>
                    <div class="flex gap-2.5 group">
                      <div class="relative flex-shrink-0">
                        <div class="w-9 h-9 rounded-full bg-gradient-to-br from-violet-600 to-purple-800 flex items-center justify-center text-white text-xs font-bold">
                          <img src="https://avatars.githubusercontent.com/u/204519754?s=130&v=4" alt="" class="w-full h-full object-cover rounded-full">
                        </div>
                      </div>
                      <div class="flex-1 min-w-0">
                        <div class="flex items-center gap-1.5 mb-0.5 flex-wrap">
                          <span class="text-xs font-semibold text-amber-400">nairha</span>
                          <span class="text-[9px] px-1.5 py-0.5 rounded bg-amber-500/20 text-amber-400 font-medium">Admin</span>
                          <span class="text-[9px] text-zinc-600">1/30/26, 8:17 PM</span>
                        </div>
                        <p class="text-sm font-bold text-white mb-1">👋 Halo Pengembang !!!</p>
                        <p class="text-[11px] text-zinc-300 leading-relaxed">
                          Selamat datang di server Discord resmi <span class="font-semibold text-white">NLFTs C-OSS</span> — ini adalah tempat untuk mengobrol tentang Dunia Web Developer, mengajukan pertanyaan, memamerkan proyek Anda, dan berkolaborasi dengan pengembang lain!!!.
                        </p>
                        <div class="mt-2 border-l-2 border-[#5865F2] bg-zinc-800/60 rounded-r px-2.5 py-1.5">
                          <p class="text-[10px] text-zinc-400 leading-relaxed">
                            📘 Kami mematuhi
                            <span class="text-[#5865F2] cursor-pointer hover:underline">Kode Etik</span> dan
                            <span class="text-[#5865F2] cursor-pointer hover:underline">Ketentuan Layanan Discord</span>.
                            Pastikan Anda telah membacanya.
                          </p>
                        </div>
                      </div>
                    </div>
                  </template>
 
                  <!-- #lobby -->
                  <template v-else-if="activeChannel === 'lobby'">
                    <div class="flex items-center gap-2 my-1">
                      <div class="flex-1 h-px bg-zinc-800" />
                      <span class="text-[9px] text-zinc-600">19 Mei 2026</span>
                      <div class="flex-1 h-px bg-zinc-800" />
                    </div>
 
                    <!-- msg 1 -->
                    <div class="flex gap-2.5">
                      <div class="w-9 h-9 rounded-full bg-gradient-to-br from-blue-500 to-cyan-600 flex items-center justify-center text-white text-xs font-bold flex-shrink-0">
                          <img src="https://avatars.githubusercontent.com/u/228851591?v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="flex items-baseline gap-1.5 mb-0.5">
                          <span class="text-xs font-semibold text-[#5865F2]">Kin You</span>
                          <span class="text-[9px] text-zinc-600">8:42 PM</span>
                        </div>
                        <p class="text-[11px] text-zinc-300 leading-relaxed">Eh gais, ada yang udah nyoba <code class="bg-zinc-700/70 text-zinc-200 rounded px-1 text-[10px]">Nuxt 4</code> belum? Alpha-nya udah keluar katanya 👀</p>
                      </div>
                    </div>
 
                    <!-- msg 2 -->
                    <div class="flex gap-2.5">
                      <div class="w-9 h-9 rounded-full bg-gradient-to-br from-rose-500 to-pink-700 flex items-center justify-center text-white text-xs font-bold flex-shrink-0">
                          <img src="https://avatars.githubusercontent.com/u/182593937?s=130&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="flex items-baseline gap-1.5 mb-0.5">
                          <span class="text-xs font-semibold text-rose-400">Tokita</span>
                          <span class="text-[9px] text-zinc-600">8:43 PM</span>
                        </div>
                        <p class="text-[11px] text-zinc-300 leading-relaxed">Udah coba kemarin! Sekarang pake unified directory baru, semua masuk ke folder <code class="bg-zinc-700/70 text-zinc-200 rounded px-1 text-[10px]">app/</code> 🔥</p>
                      </div>
                    </div>
 
                    <!-- msg 3 -->
                    <div class="flex gap-2.5">
                      <div class="w-9 h-9 rounded-full bg-gradient-to-br from-emerald-500 to-teal-700 flex items-center justify-center text-white text-xs font-bold flex-shrink-0">
                          <img src="https://avatars.githubusercontent.com/u/228840381?s=130&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="flex items-baseline gap-1.5 mb-0.5">
                          <span class="text-xs font-semibold text-emerald-400">Fakhri</span>
                          <span class="text-[9px] text-zinc-600">8:44 PM</span>
                        </div>
                        <p class="text-[11px] text-zinc-300 leading-relaxed">Wah serius? Berarti breaking change dong dari Nuxt 3? Migration guide-nya ada ga?</p>
                      </div>
                    </div>
 
                    <!-- msg 4 inline (Tokita lanjut) -->
                    <div class="flex gap-2.5">
                      <div class="w-9 h-9 rounded-full bg-gradient-to-br from-rose-500 to-pink-700 flex items-center justify-center text-white text-xs font-bold flex-shrink-0">
                          <img src="https://avatars.githubusercontent.com/u/182593937?s=130&v=4" alt="" class="w-full h-full object-cover rounded-full">  
                    </div>
                      <div>
                       <div class="flex items-baseline gap-1.5 mb-0.5">
                          <span class="text-xs font-semibold text-rose-400">Tokita</span>
                          <span class="text-[9px] text-zinc-600">8:43 PM</span>
                        </div>
                        <p class="text-[11px] text-zinc-300 leading-relaxed">Ada di docs! Yang paling beda itu auto-imports lebih strict dan performa-nya ngebut banget 🚀</p>
                      </div>
                    </div>
 
                    <!-- msg 5 -->
                    <div class="flex gap-2.5">
                      <div class="w-9 h-9 rounded-full bg-gradient-to-br from-amber-500 to-orange-600 flex items-center justify-center text-white text-xs font-bold flex-shrink-0">
                          <img src="https://avatars.githubusercontent.com/u/218329504?s=130&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="flex items-baseline gap-1.5 mb-0.5">
                          <span class="text-xs font-semibold text-amber-400">rehan</span>
                          <span class="text-[9px] text-zinc-600">8:46 PM</span>
                        </div>
                        <p class="text-[11px] text-zinc-300 leading-relaxed">gue masih nunggu stable release dulu, buat production masih ngeri kalau pake alpha 😅</p>
                      </div>
                    </div>
                  </template>
 
                  <!-- Voice: 24jam -->
                  <template v-else-if="activeChannel === 'voice-24jam'">
                    <div class="flex flex-col items-center justify-center h-full gap-3 py-6">
                      <div class="w-16 h-16 rounded-full bg-zinc-800 flex items-center justify-center">
                        <svg class="w-8 h-8 text-[#5865F2]" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3a3 3 0 0 0-3 3v6a3 3 0 0 0 6 0V6a3 3 0 0 0-3-3zm-1 13.93V19H9v2h6v-2h-2v-2.07A7.003 7.003 0 0 0 19 10h-2a5 5 0 0 1-10 0H5a7.003 7.003 0 0 0 6 6.93z"/></svg>
                      </div>
                      <div class="text-center">
                        <p class="text-xs font-semibold text-white">24-jam Non Stop</p>
                        <p class="text-[10px] text-zinc-500 mt-1">Voice aktif 24 jam — siapapun bisa join</p>
                      </div>
                      <div class="w-full space-y-1.5">
                        <p class="text-[9px] uppercase tracking-wider text-zinc-500 text-center mb-2">Online — 3</p>
                        <div v-for="u in voiceUsers24" :key="u.name" class="flex items-center gap-2 bg-zinc-800/60 rounded-lg px-2.5 py-1.5">
                          <div :class="['w-7 h-7 rounded-full flex items-center justify-center text-white text-[10px] font-bold flex-shrink-0', u.color]"> 
                            <img :src=u.initial :alt=u.initial class="w-full h-full object-cover rounded-full">
                          </div>
                          <span class="text-[11px] text-zinc-300">{{ u.name }}</span>
                          <svg v-if="u.muted" class="ml-auto w-3 h-3 text-red-400 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M19 11h-1.7c0 .74-.16 1.43-.43 2.05l1.23 1.23c.56-.98.9-2.09.9-3.28zm-4.02.17c0-.06.02-.11.02-.17V6c0-1.66-1.34-3-3-3S9 4.34 9 6v.18l5.98 5.99zM4.27 3L3 4.27l6.01 6.01V11c0 1.66 1.33 3 2.99 3 .22 0 .44-.03.65-.08l1.66 1.66c-.71.33-1.5.52-2.31.52-2.76 0-5.3-2.1-5.3-5.1H5c0 3.41 2.72 6.23 6 6.72V21h2v-3.28c.91-.13 1.77-.45 2.54-.9L19.73 21 21 19.73 4.27 3z"/></svg>
                          <svg v-else class="ml-auto w-3 h-3 text-green-400 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M12 14c1.66 0 3-1.34 3-3V5c0-1.66-1.34-3-3-3S9 3.34 9 5v6c0 1.66 1.34 3 3 3zm5.3-3c0 3-2.54 5.1-5.3 5.1S6.7 14 6.7 11H5c0 3.41 2.72 6.23 6 6.72V21h2v-3.28c3.28-.48 6-3.3 6-6.72h-1.7z"/></svg>
                        </div>
                      </div>
                      <button class="px-4 py-1.5 bg-[#5865F2] hover:bg-[#4752C4] transition rounded-lg text-[11px] font-medium text-white">
                        Bergabung ke Voice
                      </button>
                    </div>
                  </template>
 
                  <!-- Voice: vuxilabs -->
                  <template v-else-if="activeChannel === 'voice-vuxilabs'">
                    <div class="flex flex-col items-center justify-center h-full gap-3 py-6">
                      <div class="w-16 h-16 rounded-full bg-zinc-800 flex items-center justify-center">
                        <svg class="w-8 h-8 text-purple-500" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3a3 3 0 0 0-3 3v6a3 3 0 0 0 6 0V6a3 3 0 0 0-3-3zm-1 13.93V19H9v2h6v-2h-2v-2.07A7.003 7.003 0 0 0 19 10h-2a5 5 0 0 1-10 0H5a7.003 7.003 0 0 0 6 6.93z"/></svg>
                      </div>
                      <div class="text-center">
                        <p class="text-xs font-semibold text-white">vuxilabs</p>
                        <p class="text-[10px] text-zinc-500 mt-1">Channel kolaborasi tim vuxilabs</p>
                      </div>
                      <div class="w-full space-y-1.5">
                        <p class="text-[9px] uppercase tracking-wider text-zinc-500 text-center mb-2">Online — 1</p>
                        <div class="flex items-center gap-2 bg-zinc-800/60 rounded-lg px-2.5 py-1.5">
                          <div class="w-7 h-7 rounded-full bg-gradient-to-br from-purple-500 to-violet-700 flex items-center justify-center text-white text-[10px] font-bold flex-shrink-0">
                            <img src="https://avatars.githubusercontent.com/u/228332586?s=130&v=4" class="w-full h-full object-cover rounded-full">
                          </div>
                          <span class="text-[11px] text-zinc-300">Destkaa</span>
                          <svg class="ml-auto w-3 h-3 text-green-400 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M12 14c1.66 0 3-1.34 3-3V5c0-1.66-1.34-3-3-3S9 3.34 9 5v6c0 1.66 1.34 3 3 3zm5.3-3c0 3-2.54 5.1-5.3 5.1S6.7 14 6.7 11H5c0 3.41 2.72 6.23 6 6.72V21h2v-3.28c3.28-.48 6-3.3 6-6.72h-1.7z"/></svg>
                        </div>
                        <div class="flex items-center gap-2 bg-zinc-800/60 rounded-lg px-2.5 py-1.5">
                          <div class="w-7 h-7 rounded-full bg-gradient-to-br from-purple-500 to-violet-700 flex items-center justify-center text-white text-[10px] font-bold flex-shrink-0">
                            <img src="https://avatars.githubusercontent.com/u/190081649?s=130&v=4" class="w-full h-full object-cover rounded-full">
                          </div>
                          <span class="text-[11px] text-zinc-300">Cerydra</span>
                          <svg class="ml-auto w-3 h-3 text-green-400 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M12 14c1.66 0 3-1.34 3-3V5c0-1.66-1.34-3-3-3S9 3.34 9 5v6c0 1.66 1.34 3 3 3zm5.3-3c0 3-2.54 5.1-5.3 5.1S6.7 14 6.7 11H5c0 3.41 2.72 6.23 6 6.72V21h2v-3.28c3.28-.48 6-3.3 6-6.72h-1.7z"/></svg>
                        </div>
                      </div>
                      <button class="px-4 py-1.5 bg-purple-600 hover:bg-purple-700 transition rounded-lg text-[11px] font-medium text-white">
                        Bergabung ke Voice
                      </button>
                    </div>
                  </template>
 
                </div>
 
                <!-- Message Input -->
                <div v-if="!activeChannel.startsWith('voice')" class="px-3 py-2.5 border-t border-zinc-800 flex-shrink-0">
                  <div class="flex items-center gap-2 bg-zinc-800 rounded-lg px-2.5 py-2">
                    <button class="text-zinc-500 hover:text-zinc-300 transition flex-shrink-0">
                      <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm5 11h-4v4h-2v-4H7v-2h4V7h2v4h4v2z"/></svg>
                    </button>
                    <span class="flex-1 text-[10px] text-zinc-600">
                      Kirim pesan ke #{{ activeChannel === 'papan-info' ? 'papan-info' : 'lobby' }}
                    </span>
                    <button class="text-zinc-500 hover:text-zinc-300 transition flex-shrink-0">
                      <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                    </button>
                  </div>
                </div>
 
              </div>
            </div>
          </div>
        </div>
 
      </div>
    </div>
  </section>

  <!-- Section WhatsApp -->
     <section class="bg-white dark:bg-[#09090b] py-16 md:py-24 lg:py-32 text-zinc-900 dark:text-white transition-colors duration-300">
    <div class="mx-auto max-w-7xl px-4 md:px-6">
      <div class="grid items-center gap-10 lg:gap-20 lg:grid-cols-[1fr_480px]">
 
        <!-- LEFT: WhatsApp Window -->
        <div class="relative order-2 lg:order-1">
          <!-- Glow -->
          <div class="absolute inset-0 -z-10 blur-3xl opacity-20 bg-[#25D366]" />
 
          <!-- Mac Window -->
          <div class="overflow-hidden rounded-2xl border border-zinc-800 bg-[#0d0d10] shadow-[0_40px_100px_rgba(0,0,0,0.5)] w-full">
 
            <!-- Mac Header -->
            <div class="flex items-center gap-2 border-b border-zinc-800 px-5 py-4">
              <span class="h-3 w-3 rounded-full bg-red-500" />
              <span class="h-3 w-3 rounded-full bg-yellow-500" />
              <span class="h-3 w-3 rounded-full bg-green-500" />
              <div class="ml-auto text-xs text-zinc-500">WhatsApp</div>
            </div>
 
            <!-- WhatsApp Body -->
            <div class="flex h-[380px] sm:h-[430px] md:h-[480px]">
 
              <!-- Sidebar: Chat List -->
              <div class="hidden sm:flex w-[220px] md:w-[260px] border-r border-zinc-800 bg-[#111214] flex-col">
 
                <!-- WA Header -->
                <div class="flex items-center justify-between px-4 py-3 border-b border-zinc-800">
                  <div class="flex items-center gap-2">
                    <div class="w-8 h-8 rounded-full bg-gradient-to-br from-green-500 to-emerald-700 flex items-center justify-center text-white text-xs font-bold">Y</div>
                    <span class="text-sm font-semibold text-white">WhatsApp</span>
                  </div>
                  <div class="flex gap-2">
                    <button class="p-1 rounded-full hover:bg-zinc-800 text-zinc-400 hover:text-white transition">
                      <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M19 3H5c-1.1 0-2 .9-2 2v14l4-4h12c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2z"/></svg>
                    </button>
                    <button class="p-1 rounded-full hover:bg-zinc-800 text-zinc-400 hover:text-white transition">
                      <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 8c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm0 2c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm0 6c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2z"/></svg>
                    </button>
                  </div>
                </div>
 
                <!-- Search -->
                <div class="px-3 py-2 border-b border-zinc-800">
                  <div class="flex items-center gap-2 bg-zinc-800/80 rounded-full px-3 py-1.5">
                    <svg class="w-3.5 h-3.5 text-zinc-500 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/></svg>
                    <span class="text-[11px] text-zinc-500">Cari atau mulai obrolan baru</span>
                  </div>
                </div>
 
                <!-- Chat List -->
                <div class="flex-1 overflow-y-auto scrollbar-none">
                  <div
                    v-for="chat in chatList"
                    :key="chat.id"
                    @click="activeChat = chat.id"
                    :class="['flex items-center gap-3 px-4 py-3 cursor-pointer transition border-b border-zinc-800/50',
                      activeChat === chat.id ? 'bg-zinc-800/70' : 'hover:bg-zinc-800/40'
                    ]"
                  >
                    <!-- Avatar -->
                    <div class="relative flex-shrink-0">
                      <div :class="['w-11 h-11 rounded-full flex items-center justify-center text-white text-sm font-bold', chat.avatarColor]">   
                        <img :src="chat.initial" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div v-if="chat.isGroup" class="absolute -bottom-0.5 -right-0.5 w-4 h-4 rounded-full bg-[#25D366] flex items-center justify-center border-2 border-[#111214]">
                        <svg class="w-2 h-2 text-white" fill="currentColor" viewBox="0 0 24 24"><path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5c-1.66 0-3 1.34-3 3s1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5C6.34 5 5 6.34 5 8s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05 1.16.84 1.97 1.97 1.97 3.45V19h6v-2.5c0-2.33-4.67-3.5-7-3.5z"/></svg>
                      </div>
                      <div v-if="chat.online && !chat.isGroup" class="absolute -bottom-0.5 -right-0.5 w-3 h-3 rounded-full bg-[#25D366] border-2 border-[#111214]" />
                    </div>
                    <!-- Info -->
                    <div class="flex-1 min-w-0">
                      <div class="flex items-center justify-between mb-0.5">
                        <span class="text-xs font-semibold text-white truncate">{{ chat.name }}</span>
                        <span :class="['text-[9px] flex-shrink-0 ml-1', chat.unread ? 'text-[#25D366]' : 'text-zinc-600']">{{ chat.time }}</span>
                      </div>
                      <div class="flex items-center gap-1">
                        <svg v-if="chat.sent" class="w-3 h-3 text-[#25D366] flex-shrink-0" fill="currentColor" viewBox="0 0 24 24"><path d="M18 7l-1.41-1.41-6.34 6.34 1.41 1.41L18 7zm4.24-1.41L11.66 16.17 7.48 12l-1.41 1.41L11.66 19l12-12-1.42-1.41zM.41 13.41L6 19l1.41-1.41L1.83 12 .41 13.41z"/></svg>
                        <p class="text-[10px] text-zinc-500 truncate">{{ chat.lastMsg }}</p>
                        <span v-if="chat.unread" class="ml-auto flex-shrink-0 bg-[#25D366] text-black text-[9px] font-bold rounded-full w-4 h-4 flex items-center justify-center">{{ chat.unread }}</span>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
 
              <!-- Main Chat Area -->
              <div class="flex-1 flex flex-col min-w-0" :style="{ backgroundImage: 'radial-gradient(circle, #1a1f1a 1px, transparent 1px)', backgroundSize: '24px 24px', backgroundColor: '#0d1117' }">
 
                <!-- Chat Header -->
                <div class="flex items-center gap-3 px-4 py-3 border-b border-zinc-800 bg-[#111214] flex-shrink-0">
                  <template v-if="currentChat">
                    <div :class="['w-9 h-9 rounded-full flex items-center justify-center text-white text-xs font-bold flex-shrink-0', currentChat.avatarColor]">
                        <img :src="currentChat.initial" alt="" class="w-full h-full object-cover rounded-full">
                    </div>
                    <div class="flex-1 min-w-0">
                      <p class="text-xs font-semibold text-white">{{ currentChat.name }}</p>
                      <p class="text-[10px] text-[#25D366]">{{ currentChat.subtitle }}</p>
                    </div>
                    <div class="flex gap-1 flex-shrink-0">
                      <button class="p-1.5 rounded-full hover:bg-zinc-800 text-zinc-400 hover:text-white transition">
                        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M20 2H4c-1.1 0-2 .9-2 2v18l4-4h14c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zm0 14H5.17L4 17.17V4h16v12z"/></svg>
                      </button>
                      <button class="p-1.5 rounded-full hover:bg-zinc-800 text-zinc-400 hover:text-white transition">
                        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 8c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2 .9 2 2 2zm0 2c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm0 6c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2z"/></svg>
                      </button>
                    </div>
                  </template>
                </div>
 
                <!-- Messages -->
                <div class="flex-1 overflow-y-auto px-4 py-4 space-y-1.5 scrollbar-none">
                  <template v-if="activeChat === 'fts-group'">
 
                    <!-- Date label -->
                    <div class="flex justify-center my-3">
                      <span class="text-[10px] text-zinc-400 bg-zinc-800/70 rounded-full px-3 py-1">HARI INI</span>
                    </div>
 
                    <!-- System message: joined -->
                    <div class="flex justify-center my-2">
                      <span class="text-[10px] text-zinc-400 bg-zinc-800/70 rounded-lg px-3 py-1 text-center">
                        plana menambahkan Anda ke grup
                      </span>
                    </div>
 
                    <!-- msg: davingm (sender, kiri) -->
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-violet-600 to-purple-800 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://avatars.githubusercontent.com/u/228851591?s=96&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2 text-left">
                          <p class="text-[10px] font-semibold text-violet-400 mb-0.5">davingm</p>
                          <p class="text-[11px] text-zinc-200 leading-relaxed">Selamat datang semua di grup <span class="font-semibold text-[#25D366]">NLFTs C-OSS</span>! 🎉 Ini tempat kita ngobrol soal web dev, share project, dan kolaborasi bareng.</p>
                          <p class="text-[9px] text-zinc-600 mt-1 text-right">08.17 ✓✓</p>
                        </div>
                      </div>
                    </div>
 
                    <!-- msg: Tokita (kiri) -->
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-rose-500 to-pink-700 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://avatars.githubusercontent.com/u/216720543?s=96&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                          <p class="text-[10px] font-semibold text-rose-400 mb-0.5">Fandy.dev</p>
                          <p class="text-[11px] text-zinc-200">Sip siap! Ada agenda apa dulu nih semua? 🙌</p>
                          <p class="text-[9px] text-zinc-600 mt-1 text-right">08.19 ✓✓</p>
                        </div>
                      </div>
                    </div>
 
                    <!-- msg: plana (kiri) -->
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-blue-500 to-cyan-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://avatars.githubusercontent.com/u/226198461?s=96&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                          <p class="text-[10px] font-semibold text-blue-400 mb-0.5">radietya pratama</p>
                          <p class="text-[11px] text-zinc-200">Rencananya mau bikin open-source project bareng, stack-nya Vue + Nuxt 4. Ada yang mau ikut? 😄</p>
                          <p class="text-[9px] text-zinc-600 mt-1 text-right">08.21 ✓✓</p>
                        </div>
                      </div>
                    </div>
 
                    <!-- msg: SiloKusuma (kiri) -->
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-emerald-500 to-teal-700 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://avatars.githubusercontent.com/u/202130049?s=96&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                          <p class="text-[10px] font-semibold text-emerald-400 mb-0.5">Vahllzzz</p>
                          <p class="text-[11px] text-zinc-200">Count me in! Nuxt 4 lagi hot banget, gue udah ngintip alpha-nya kemarin 🔥</p>
                          <p class="text-[9px] text-zinc-600 mt-1 text-right">08.23 ✓✓</p>
                        </div>
                      </div>
                    </div>
 
                    <!-- msg: rehan (kiri) -->
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-amber-500 to-orange-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://avatars.githubusercontent.com/u/226198461?s=96&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                          <p class="text-[10px] font-semibold text-amber-400 mb-0.5">radietya</p>
                          <p class="text-[11px] text-zinc-200">Gue juga! Btw Discord server-nya juga udah siap ya? Biar bisa diskusi lebih lanjut di sana 👀</p>
                          <p class="text-[9px] text-zinc-600 mt-1 text-right">08.25 ✓✓</p>
                        </div>
                      </div>
                    </div>
 
                    <!-- msg: davingm (kiri) reply -->
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-violet-600 to-purple-800 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://avatars.githubusercontent.com/u/228839856?s=96&v=4" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div>
                        <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                          <p class="text-[10px] font-semibold text-violet-400 mb-0.5">teguh</p>
                          <!-- Quote reply -->
                          <div class="border-l-2 border-[#25D366] bg-zinc-800/60 rounded-r px-2 py-1 mb-1.5">
                            <p class="text-[9px] text-[#25D366] font-medium">rehan ram</p>
                            <p class="text-[9px] text-zinc-400 truncate">Discord server-nya juga udah siap ya?</p>
                          </div>
                          <p class="text-[11px] text-zinc-200">Udah bang! Link-nya bisa dicek di papan-info. Let's build something great bareng! 🚀</p>
                          <p class="text-[9px] text-zinc-600 mt-1 text-right">08.27 ✓✓</p>
                        </div>
                      </div>
                    </div>
 
                    <!-- msg: YOU (kanan, hijau) -->
                    <div class="flex justify-end">
                      <div class="max-w-[75%]">
                        <div class="bg-[#005c4b] rounded-2xl rounded-tr-sm px-3 py-2">
                          <p class="text-[11px] text-zinc-200">Siap ikutan! Link Discord-nya udah gue save. See you guys di server 🙌</p>
                          <div class="flex items-center justify-end gap-1 mt-1">
                            <p class="text-[9px] text-zinc-400">08.30</p>
                            <svg class="w-3 h-3 text-[#25D366]" fill="currentColor" viewBox="0 0 24 24"><path d="M18 7l-1.41-1.41-6.34 6.34 1.41 1.41L18 7zm4.24-1.41L11.66 16.17 7.48 12l-1.41 1.41L11.66 19l12-12-1.42-1.41zM.41 13.41L6 19l1.41-1.41L1.83 12 .41 13.41z"/></svg>
                          </div>
                        </div>
                      </div>
                    </div>
 
                  </template>
 
                  <!-- Chat: plana DM -->
                  <template v-else-if="activeChat === 'plana-dm'">
                    <div class="flex justify-center my-3">
                      <span class="text-[10px] text-zinc-400 bg-zinc-800/70 rounded-full px-3 py-1">KEMARIN</span>
                    </div>
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-blue-500 to-cyan-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="/team/siro.webp" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                        <p class="text-[11px] text-zinc-200">Bang Media Sosial NLFTs udah selesai dibuat nih. udah di cek belum? 😄</p>
                        <p class="text-[9px] text-zinc-600 mt-1 text-right">19.42 ✓✓</p>
                      </div>
                    </div>
                    <div class="flex justify-end">
                      <div class="max-w-[75%]">
                        <div class="bg-[#005c4b] rounded-2xl rounded-tr-sm px-3 py-2">
                          <p class="text-[11px] text-zinc-200">Belum sempet, belum di cek sama bang rehan. Baru pulang dia, paling besok 😅</p>
                          <div class="flex items-center justify-end gap-1 mt-1">
                            <p class="text-[9px] text-zinc-400">19.43</p>
                            <svg class="w-3 h-3 text-[#25D366]" fill="currentColor" viewBox="0 0 24 24"><path d="M18 7l-1.41-1.41-6.34 6.34 1.41 1.41L18 7zm4.24-1.41L11.66 16.17 7.48 12l-1.41 1.41L11.66 19l12-12-1.42-1.41zM.41 13.41L6 19l1.41-1.41L1.83 12 .41 13.41z"/></svg>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-blue-500 to-cyan-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <div class="w-6 h-6 rounded-full bg-gradient-to-br from-blue-500 to-cyan-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="/team/siro.webp" alt="" class="w-full h-full object-cover rounded-full">
                      </div>
                      </div>
                      <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                        <p class="text-[11px] text-zinc-200">Aman, siap bang! 👍</p>
                        <p class="text-[9px] text-zinc-600 mt-1 text-right">19.44 ✓✓</p>
                      </div>
                    </div>
                  </template>
 
                  <!-- Chat: rehan DM -->
                  <template v-else-if="activeChat === 'rehan-dm'">
                    <div class="flex justify-center my-3">
                      <span class="text-[10px] text-zinc-400 bg-zinc-800/70 rounded-full px-3 py-1">HARI INI</span>
                    </div>
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-amber-500 to-orange-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://github.com/BeedBest.png" alt="Habsy" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                        <p class="text-[11px] text-zinc-200">Bang mau Nyoba Praktikin Topologi yang kemaren kita buat di cisco? </p>
                        <p class="text-[9px] text-zinc-600 mt-1 text-right">02.00 ✓✓</p>
                      </div>
                    </div>
                    <div class="flex justify-end">
                      <div class="max-w-[75%]">
                        <div class="bg-[#005c4b] rounded-2xl rounded-tr-sm px-3 py-2">
                          <p class="text-[11px] text-zinc-200">Kenapa harus jam 2 subuh woi 😭. nanti aku datang ke ruang server agak telat</p>
                          <div class="flex items-center justify-end gap-1 mt-1">
                            <p class="text-[9px] text-zinc-400">02.10</p>
                            <svg class="w-3 h-3 text-[#25D366]" fill="currentColor" viewBox="0 0 24 24"><path d="M18 7l-1.41-1.41-6.34 6.34 1.41 1.41L18 7zm4.24-1.41L11.66 16.17 7.48 12l-1.41 1.41L11.66 19l12-12-1.42-1.41zM.41 13.41L6 19l1.41-1.41L1.83 12 .41 13.41z"/></svg>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-amber-500 to-orange-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://github.com/BeedBest.png" alt="Habsy" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                        <p class="text-[11px] text-zinc-200">Maaf Bang, soalnya saya gak bisa tidur takut lupa </p>
                        <p class="text-[9px] text-zinc-600 mt-1 text-right">02.20 ✓✓</p>
                      </div>
                    </div>
                    <div class="flex gap-2 max-w-[85%]">
                      <div class="w-6 h-6 rounded-full bg-gradient-to-br from-amber-500 to-orange-600 flex items-center justify-center text-white text-[9px] font-bold flex-shrink-0 mt-1">
                        <img src="https://github.com/BeedBest.png" alt="Habsy" class="w-full h-full object-cover rounded-full">
                      </div>
                      <div class="bg-[#1f2c34] rounded-2xl rounded-tl-sm px-3 py-2">
                        <p class="text-[11px] text-zinc-200">siap, di tunggu yaa bang </p>
                        <p class="text-[9px] text-zinc-600 mt-1 text-right">02.20 ✓✓</p>
                      </div>
                    </div>
                  </template>
 
                </div>
 
                <!-- Input Bar -->
                <div class="px-3 py-2.5 border-t border-zinc-800 bg-[#111214] flex-shrink-0">
                  <div class="flex items-center gap-2">
                    <button class="p-1.5 rounded-full hover:bg-zinc-700 text-zinc-400 hover:text-white transition">
                      <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zm3.23 14.29L11 13.41V7h2v5.58l3.77 3.71-1.55 1z"/></svg>
                    </button>
                    <div class="flex-1 flex items-center gap-2 bg-zinc-800 rounded-full px-3 py-2">
                      <button class="text-zinc-500 hover:text-zinc-300 transition flex-shrink-0">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
                      </button>
                      <span class="flex-1 text-[10px] text-zinc-600">Ketik pesan</span>
                      <button class="text-zinc-500 hover:text-zinc-300 transition flex-shrink-0">
                        <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M16.5 6.75h-9A2.25 2.25 0 005.25 9v7.5A2.25 2.25 0 007.5 18.75h9a2.25 2.25 0 002.25-2.25V9a2.25 2.25 0 00-2.25-2.25zM12 9.75a2.25 2.25 0 110 4.5 2.25 2.25 0 010-4.5zM7.5 15.75a.75.75 0 01-.75-.75v-1.5a.75.75 0 011.5 0v1.5a.75.75 0 01-.75.75z"/></svg>
                      </button>
                    </div>
                    <button class="p-2 rounded-full bg-[#25D366] hover:bg-[#20ba58] transition text-white flex-shrink-0">
                      <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3a3 3 0 0 0-3 3v6a3 3 0 0 0 6 0V6a3 3 0 0 0-3-3zm-1 13.93V19H9v2h6v-2h-2v-2.07A7.003 7.003 0 0 0 19 10h-2a5 5 0 0 1-10 0H5a7.003 7.003 0 0 0 6 6.93z"/></svg>
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
 
        <!-- RIGHT: Text & CTA -->
        <div class="max-w-lg order-1 lg:order-2">
          <span class="mb-6 inline-flex rounded-full border border-zinc-200 dark:border-zinc-800 px-4 py-1 text-xs tracking-[0.2em] uppercase text-zinc-500">
            Community
          </span>
          <h2 class="text-4xl font-semibold leading-tight tracking-tight md:text-5xl text-zinc-950 dark:text-white">
            Gabung Grup
            <span class="text-[#25D366]">WhatsApp</span>
          </h2>
          <p class="mt-8 text-base leading-8 text-zinc-600 dark:text-zinc-400">
            Komunikasi cepat dan santai dengan komunitas lokal. Dapatkan update acara, pengumuman terbaru, dan ngobrol langsung bareng anggota kapan saja.
          </p>
          <div class="mt-8 md:mt-10 flex flex-wrap gap-3 md:gap-4">
            <NuxtLink
              to="/wa"
              external
              target="_blank"
              class="rounded-xl bg-[#25D366] px-7 py-3 text-sm font-medium text-black transition hover:opacity-90 flex items-center gap-2"
            >
              <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
              Gabung Grup
            </NuxtLink>
            <NuxtLink
              to="/docs/getting-started#2-grup-whatsapp-terbuka-dengan-syarat"
              class="rounded-xl border border-zinc-300 dark:border-zinc-800 px-7 py-3 text-sm font-medium text-zinc-700 dark:text-zinc-300 transition hover:bg-zinc-100 dark:hover:bg-zinc-900/50 hover:border-zinc-400 dark:hover:border-zinc-700"
            >
              Pelajari Lebih Lanjut
            </NuxtLink>
          </div>
 
          <!-- Stats -->
          <div class="mt-12 grid grid-cols-3 gap-6 border-t border-zinc-200 dark:border-zinc-800 pt-8">
            <div>
              <p class="text-2xl font-semibold text-zinc-950 dark:text-white">120+</p>
              <p class="text-xs text-zinc-500 mt-1">Anggota Aktif</p>
            </div>
            <div>
              <p class="text-2xl font-semibold text-zinc-950 dark:text-white">24/7</p>
              <p class="text-xs text-zinc-500 mt-1">Selalu Online</p>
            </div>
            <div>
              <p class="text-2xl font-semibold text-[#25D366]">Free</p>
              <p class="text-xs text-zinc-500 mt-1">Gratis Selamanya</p>
            </div>
          </div>
        </div>
 
      </div>
    </div>
  </section>
 
  <!-- Section GitHub Discussion -->
  <section class="py-16 md:py-24 lg:py-32 bg-zinc-50 dark:bg-black/20 border-t border-zinc-200 dark:border-zinc-800 transition-colors duration-300">
    <div class="mx-auto max-w-7xl px-6">
      <div class="mb-16 text-center max-w-2xl mx-auto space-y-4">
        <span class="inline-flex rounded-full border border-zinc-200 dark:border-zinc-800 px-4 py-1 text-xs tracking-[0.2em] uppercase text-zinc-500">
          Collaboration
        </span>
        <h2 class="text-4xl font-semibold leading-tight tracking-tight md:text-5xl text-zinc-950 dark:text-white">
          Diskusi Terbuka di <span class="text-[#f78166]">GitHub</span>
        </h2>
        <p class="text-base text-zinc-600 dark:text-zinc-400">
          Ikuti diskusi teknis, bagikan ide, atau ajukan pertanyaan langsung di forum diskusi repositori GitHub resmi kami.
        </p>
      </div>
      <Githubdiscussion />
    </div>
  </section>
 
<section class="relative px-4 md:px-6 py-16 md:py-24 bg-black dark:bg-white text-zinc-900 dark:text-zinc-100 text-center overflow-hidden border-t border-zinc-200 dark:border-zinc-800 transition-colors duration-300">
  <div class="absolute left-0 bottom-0 w-64 h-64 hidden lg:block translate-x-[-10%] translate-y-[10%]">
      <img src="/images/arisu.webp" alt="Kei Chibi" class="w-full h-full object-contain" />
    </div>

    <div class="absolute right-0 bottom-0 w-64 h-64 hidden lg:block translate-x-[10%] translate-y-[10%]">
      <img src="/images/kei.webp" alt="Arisu Chibi" class="w-full h-full object-contain" />
    </div>

    <div class="relative z-10 max-w-2xl mx-auto space-y-8">
      <h2 class="text-3xl md:text-4xl font-light text-zinc-950 dark:text-black">
        Siap berkontribusi?
      </h2>
      <p class="text-zinc-600 dark:text-zinc-400">
        Setiap kode yang Anda bagikan dan setiap diskusi yang Anda ikuti membantu Indonesia menjadi lebih mandiri secara teknologi.
      </p>
      <NuxtLink
        to="/docs/getting-started#cara-berkontribusi"
        class="inline-block px-8 py-4 bg-zinc-900 dark:bg-black text-white dark:text-white rounded-xl font-medium hover:opacity-90 transition-opacity"
      >
        Mulai Sekarang
      </NuxtLink>
    </div>
  </section>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue';
import { gsap } from 'gsap'
import { SplitText } from 'gsap/SplitText'

gsap.registerPlugin(SplitText)

const headerRef = ref<HTMLElement | null>(null)
const glowRef = ref<HTMLElement | null>(null)
const lineRef = ref<HTMLElement | null>(null)
const titleRef = ref<HTMLElement | null>(null)
const subRef = ref<HTMLElement | null>(null)

function onMouseMove(e: MouseEvent) {
  if (!headerRef.value || !glowRef.value) return

  const rect = headerRef.value.getBoundingClientRect()
  gsap.to(glowRef.value, {
    x: e.clientX - rect.left,
    y: e.clientY - rect.top,
    duration: 0.8,
    ease: 'power3.out'
  })
}

onMounted(() => {
  // Split judul jadi kata per kata (biar tetap rapi wrapping-nya)
  const split = SplitText.create(titleRef.value, {
    type: 'words,lines',
    mask: 'lines', // otomatis kasih overflow-hidden per baris -> efek "naik dari bawah"
    linesClass: 'split-line'
  })

  const tl = gsap.timeline({ defaults: { ease: 'power4.out' } })

  tl.fromTo(
    lineRef.value,
    { width: 0 },
    { width: 64, duration: 0.6, ease: 'power2.inOut' }
  )
    .from(
      split.words,
      {
        yPercent: 120,
        opacity: 0,
        filter: 'blur(8px)',
        duration: 1.1,
        stagger: 0.06
      },
      '-=0.2'
    )
    .to(
      subRef.value,
      {
        opacity: 1,
        y: 0,
        duration: 0.8
      },
      '-=0.5'
    )
    .from(
      subRef.value,
      { y: 12 },
      '<'
    )
})

useSeoMeta({
  title: 'Terhubung dengan NLFTs — Komunitas Developer Indonesia',
  ogTitle: 'Terhubung dengan NLFTs — Komunitas Developer Indonesia',
  description: 'Hubungi dan bergabunglah dengan ekosistem NLFTs melalui Discord, WhatsApp Group, atau kontribusi GitHub. Temukan cara terbaik untuk terhubung dengan komunitas developer 24 jam non-stop.',
  ogDescription: 'Hubungi dan bergabunglah dengan ekosistem NLFTs melalui Discord, WhatsApp Group, atau kontribusi GitHub. Temukan cara terbaik untuk terhubung dengan komunitas developer 24 jam non-stop.',
  ogImage: 'https://nlfts.dev/og/link.png',
  ogImageWidth: 1200,
  ogImageHeight: 630,
  ogImageType: 'image/png',
  ogUrl: 'https://nlfts.dev/terhubung',
  ogType: 'website',
  twitterCard: 'summary_large_image',
  twitterTitle: 'Terhubung dengan NLFTs — Komunitas Developer Indonesia',
  twitterDescription: 'Hubungi dan bergabunglah dengan ekosistem NLFTs melalui Discord, WhatsApp Group, atau kontribusi GitHub. Temukan cara terbaik untuk terhubung dengan komunitas developer 24 jam non-stop.',
  twitterImage: 'https://nlfts.dev/og/link.png',
})

const contactMethods = ref([
  { 
    name: 'GitHub', 
    description: 'Akses repositori open-source kami, laporkan masalah, atau kirimkan kontribusi kode Anda secara langsung.', 
    action: 'Lihat Repositori' 
  },
  { 
    name: 'Discord', 
    description: 'Bergabunglah dalam diskusi real-time, sesi tanya jawab teknis, dan networking antar developer.', 
    action: 'Masuk Server' 
  },
  { 
    name: 'WhatsApp Group', 
    description: 'Komunikasi cepat dan santai dengan komunitas lokal untuk informasi acara dan pengumuman terbaru.', 
    action: 'Gabung Grup' 
  }
]);

 
const activeChannel = ref('papan-info')
 
const categories = ref({
  info: true,
  text: true,
  voice: true
})
 
function toggleCategory(key: 'info' | 'text' | 'voice') {
  categories.value[key] = !categories.value[key]
}
 
const voiceUsers24 = ref([
  { name: 'Sidikqst', initial: 'https://avatars.githubusercontent.com/u/230048582?s=130&v=4', color: 'bg-gradient-to-br from-blue-500 to-cyan-600', muted: false },
  { name: 'davingm', initial: 'https://avatars.githubusercontent.com/u/228851591?v=4', color: 'bg-gradient-to-br from-rose-500 to-pink-700', muted: true },
  { name: 'Bara', initial: 'https://github.com/barabr0.png', color: 'bg-gradient-to-br from-amber-500 to-orange-600', muted: false },
])



const activeChat = ref('fts-group')
 
const chatList = ref([
  {
    id: 'fts-group',
    name: 'NLFTs C-OSS 🚀',
    initial: './team/nlfts.webp',
    avatarColor: 'bg-gradient-to-br from-[#25D366] to-emerald-700',
    isGroup: true,
    lastMsg: 'Anda: See you guys di server 🙌',
    time: '08.30',
    unread: 0,
    sent: true,
    subtitle: 'plana, Tokita, SiloKusuma, rehan +2',
  },
  {
    id: 'plana-dm',
    name: 'ashiro-tanka',
    initial: './team/siro.webp',
    avatarColor: 'bg-gradient-to-br from-blue-500 to-cyan-600',
    isGroup: false,
    online: true,
    lastMsg: 'Aman, siap bang! 👍',
    time: '19.44',
    unread: 0,
    sent: false,
    subtitle: 'online',
  },
  {
    id: 'rehan-dm',
    name: 'ajrin',
    initial: 'https://github.com/BeedBest.png',
    avatarColor: 'bg-gradient-to-br from-amber-500 to-orange-600',
    isGroup: false,
    online: false,
    lastMsg: 'siap, ini lagi install Cargo',
    time: '20.13',
    unread: 2,
    sent: true,
    subtitle: 'terakhir dilihat hari ini pukul 20.13',
  },
])
 
const currentChat = computed(() => chatList.value.find(c => c.id === activeChat.value))
</script>