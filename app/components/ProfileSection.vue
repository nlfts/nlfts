<template>
  <section class="border-b border-zinc-200 bg-white py-20 transition-colors duration-300 dark:border-zinc-800 dark:bg-[#09090b] sm:py-28">
    <UContainer>
      <div class="grid gap-14 lg:grid-cols-[1.05fr_0.95fr] lg:gap-20">
        <div>
          <div class="mb-8 flex items-center gap-3 text-xs font-semibold uppercase tracking-[0.2em] text-[#ff5b22]">
            <span class="h-2 w-2 rounded-full bg-[#ff5b22]" />
            Apa ini?
          </div>
          <h2 class="max-w-[680px] text-4xl font-semibold leading-[0.98] tracking-[-0.055em] text-zinc-900 dark:text-zinc-100 sm:text-6xl">
            Tempat developer tumbuh untuk Indonesia moderen
          </h2>
          <p class="mt-8 max-w-[590px] text-base leading-relaxed text-zinc-600 dark:text-zinc-400 sm:text-lg">
            NLFTs adalah komunitas developer dan perusahaan teknologi yang mempertemukan orang-orang dengan rasa ingin tahu tinggi untuk membuat produk digital yang bermakna.
          </p>
          <p class="mt-4 max-w-[590px] text-base leading-relaxed text-zinc-600 dark:text-zinc-400 sm:text-lg">
            Kami percaya teknologi terbaik lahir dari diskusi terbuka, eksperimen berani, dan ekosistem yang saling mendukung.
          </p>

          <div class="mt-9 flex flex-wrap gap-3">
            <NuxtLink to="/terhubung" class="inline-flex items-center gap-3 rounded-full bg-zinc-900 px-5 py-3 text-sm font-semibold text-white transition-colors hover:bg-[#ff5b22] dark:bg-white dark:text-zinc-900 dark:hover:bg-[#ff5b22]">
              Bergabung dengan kami
              <UIcon name="i-lucide-arrow-up-right" class="h-4 w-4" />
            </NuxtLink>
            <NuxtLink to="/about" class="inline-flex items-center gap-3 rounded-full border border-zinc-300 px-5 py-3 text-sm font-semibold text-zinc-800 transition-colors hover:border-zinc-900 hover:bg-zinc-100 dark:border-zinc-700 dark:text-zinc-200 dark:hover:border-zinc-300 dark:hover:bg-zinc-900">
              Kenali NLFTs
            </NuxtLink>
          </div>
        </div>

        <div class="flex flex-col gap-5">
          <div class="relative aspect-[4/3] overflow-hidden rounded-[10px] bg-zinc-100 dark:bg-zinc-900">
            <NuxtImg
              src="/location/indo.webp"
              alt="Tim developer berkolaborasi"
              width="700"
              height="525"
              loading="lazy"
              class="h-full w-full object-cover grayscale transition-all duration-700 hover:scale-105 hover:grayscale-0"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/45 via-transparent to-transparent" />
            <span class="absolute bottom-5 left-5 text-xs uppercase tracking-[0.18em] text-white/80">NLFTs Indonesia</span>
          </div>
          <div class="grid grid-cols-3 divide-x divide-zinc-200 rounded-[10px] border border-zinc-200 bg-zinc-50 dark:divide-zinc-800 dark:border-zinc-800 dark:bg-zinc-950">
            <div class="p-4 sm:p-5">
              <strong class="block text-2xl font-semibold tracking-tight text-zinc-900 dark:text-white">100+</strong>
              <span class="mt-1 block text-xs text-zinc-500">Developer</span>
            </div>
            <div class="p-4 sm:p-5">
              <strong class="block text-2xl font-semibold tracking-tight text-zinc-900 dark:text-white">24/7</strong>
              <span class="mt-1 block text-xs text-zinc-500">Kolaborasi</span>
            </div>
            <div class="p-4 sm:p-5">
              <strong class="block text-2xl font-semibold tracking-tight text-zinc-900 dark:text-white">Open</strong>
              <span class="mt-1 block text-xs text-zinc-500">Mindset</span>
            </div>
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>