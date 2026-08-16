<script setup lang="ts">
import type { NuxtError } from '#app'

defineProps<{
  error: NuxtError
}>()
</script>

<template>
  <div class="min-h-screen flex items-center justify-center bg-white dark:bg-zinc-900 relative overflow-hidden">

    <!-- Gambar di belakang teks -->

<div class="absolute inset-0 flex items-center justify-center pointer-events-none">
  <div class="w-72 h-92 md:w-96 md:h-[22rem] overflow-hidden opacity-20">
    <img
      src="/images/404.png"
      alt="Background"
      class="w-full h-full object-contain"
    />
  </div>
</div>



    <!-- Konten -->
    <div class="text-center p-8 relative z-10 max-w-lg">
      <p class="text-sm text-zinc-500 dark:text-zinc-400 mb-2">
        Error {{ error?.statusCode || 404 }}
      </p>

      <h1 class="text-3xl font-semibold text-zinc-900 dark:text-zinc-50 mb-4">
        {{ error?.statusCode === 404
          ? 'Halaman tidak ditemukan'
          : 'Terjadi kesalahan'
        }}
      </h1>

      <p class="text-base text-zinc-600 dark:text-zinc-400 mb-6">
        {{ error?.message || 'Permintaan Anda tidak dapat diproses.' }}
      </p>

      <div class="flex gap-4 justify-center">
        <NuxtLink
          to="/"
          class="px-4 py-2 bg-zinc-100 dark:bg-zinc-800 rounded"
        >
          Kembali ke Beranda
        </NuxtLink>

        <button
          class="px-4 py-2 border rounded"
          @click="$router.back()"
        >
          Halaman Sebelumnya
        </button>
      </div>
    </div>

  </div>
</template>