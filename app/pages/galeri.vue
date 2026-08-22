<template>
  <div class="min-h-screen bg-white dark:bg-[#09090b] font-sans transition-colors duration-200">

    <!-- ─── HEADER ──────────────────────────────────────────── -->
    <header class="sticky top-0 z-30 border-b border-zinc-200 dark:border-zinc-800 bg-white/90 dark:bg-[#09090b]/90 backdrop-blur-sm">
      <div class="max-w-screen-xl mx-auto px-6 h-12 flex items-center justify-between">
        <span class="text-[11px] font-medium tracking-[0.1em] uppercase text-zinc-400 dark:text-zinc-600 shrink-0">
          Gallery
        </span>
        <span class="text-[11px] font-medium tracking-[0.06em] text-zinc-400 dark:text-zinc-600 shrink-0 tabular-nums">
          {{ filteredImages.length }} foto
        </span>
      </div>
    </header>

    <!-- ─── HERO ─────────────────────────────────────────────── -->
    <section class="max-w-screen-xl mx-auto px-6 pt-10 pb-8 sm:pt-14 sm:pb-10">
      <div class="overflow-hidden rounded-[28px] border border-zinc-200/80 dark:border-zinc-800/80 bg-gradient-to-br from-zinc-50 via-white to-zinc-100 dark:from-zinc-950 dark:via-black dark:to-zinc-900 shadow-[0_20px_80px_rgba(0,0,0,0.06)] dark:shadow-[0_20px_80px_rgba(0,0,0,0.35)]">
        <div class="grid gap-8 px-6 py-8 sm:px-8 sm:py-10 lg:grid-cols-[1.15fr_0.85fr] lg:items-end lg:px-10 lg:py-12">
          <div class="max-w-2xl">
            <p class="mb-3 text-[11px] font-medium uppercase tracking-[0.24em] text-zinc-500 dark:text-zinc-500">
              Gallery
            </p>
            <h1 class="text-3xl font-semibold tracking-[-0.03em] text-zinc-950 dark:text-zinc-50 sm:text-4xl lg:text-5xl">
              Menyimpan momen, karya, dan proses di satu tempat.
            </h1>
            <p class="mt-4 max-w-xl text-sm leading-7 text-zinc-600 dark:text-zinc-400 sm:text-[15px]">
              Dokumentasi visual dari proyek, desain, event, dan behind the scenes yang membentuk identitas NLFTs.
            </p>
          </div>

          <div class="flex items-end justify-start lg:justify-end">
            <div class="relative flex h-48 w-full max-w-[380px] items-end justify-end overflow-hidden rounded-[24px] bg-transparent sm:h-56">
              <img
                src="/images/galeri.png"
                alt="Galeri NLFTs"
                class="h-[145%] w-[145%] object-contain object-bottom translate-x-[8%] translate-y-[12%]"
              />
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ─── SUBHEADER ───────────────────────────────────────── -->
    <section class="max-w-screen-xl mx-auto border-x border-b border-zinc-200/80 dark:border-zinc-800/80 bg-white/80 dark:bg-[#09090b]/80 px-6 py-3 backdrop-blur-sm">
      <div class="flex flex-wrap items-center justify-between gap-3">
        <nav class="flex flex-wrap items-center gap-1">
          <button
            v-for="f in filters"
            :key="f.key"
            @click="activeFilter = f.key"
            class="rounded-full px-3 py-1.5 text-[12px] font-medium transition-colors duration-150"
            :class="activeFilter === f.key
              ? 'bg-zinc-950 text-white dark:bg-zinc-100 dark:text-zinc-950'
              : 'text-zinc-500 hover:text-zinc-900 dark:text-zinc-500 dark:hover:text-zinc-200'"
          >
            {{ f.label }}
          </button>
        </nav>
        <span class="text-[11px] uppercase tracking-[0.16em] text-zinc-400 dark:text-zinc-600">
          Visual archive
        </span>
      </div>
    </section>

    <!-- ─── MASONRY GRID ─────────────────────────────────────── -->
    <main class="max-w-screen-xl mx-auto">
      <div class="border-x border-zinc-200 dark:border-zinc-800">
        <div class="flex min-h-[320px] flex-col items-center justify-center gap-3 border-b border-zinc-200/80 px-6 py-24 text-center dark:border-zinc-800/80">
          <div class="flex h-12 w-12 items-center justify-center rounded-full border border-zinc-200 bg-zinc-50 text-zinc-400 dark:border-zinc-800 dark:bg-zinc-950 dark:text-zinc-600">
            <svg class="h-5 w-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
              <rect x="3" y="3" width="18" height="18" rx="2" />
              <circle cx="8.5" cy="8.5" r="1.5" />
              <path d="M21 15l-5-5L5 21" />
            </svg>
          </div>
          <p class="text-[15px] font-medium text-zinc-900 dark:text-zinc-100">Belum ada gambar yang diposting</p>
          <p class="max-w-md text-sm leading-6 text-zinc-500 dark:text-zinc-400">
            Galeri ini sedang kosong. Nantikan konten visual yang akan ditambahkan segera.
          </p>
        </div>
      </div>
    </main>

    <!-- ─── FOOTER ───────────────────────────────────────────── -->
    <footer class="max-w-screen-xl mx-auto border-x border-t border-zinc-200 dark:border-zinc-800 px-6 py-5 flex items-center justify-between">
      <span class="text-[11px] text-zinc-400 dark:text-zinc-600">NLFTs · Dokumentasi Visual</span>
      <span class="text-[11px] text-zinc-300 dark:text-zinc-700 tabular-nums">{{ new Date().getFullYear() }}</span>
    </footer>

    <!-- ─── LIGHTBOX ──────────────────────────────────────────── -->
    <Teleport to="body">
      <Transition name="lb">
        <div
          v-if="lightbox"
          class="fixed inset-0 z-50 bg-white/98 dark:bg-[#09090b]/98 flex flex-col"
          @keydown.esc="closeLightbox"
          tabindex="-1"
          ref="lbEl"
        >
          <!-- Lightbox header -->
          <div class="flex items-center justify-between px-6 h-12 border-b border-zinc-200 dark:border-zinc-800 shrink-0">
            <div class="flex items-center gap-4">
              <span class="text-[11px] font-medium tracking-[0.1em] uppercase text-zinc-400 dark:text-zinc-600">Gallery</span>
              <span class="text-[11px] text-zinc-300 dark:text-zinc-700">/</span>
              <span class="text-[12px] font-medium text-zinc-900 dark:text-zinc-100">{{ lightbox.title }}</span>
            </div>
            <div class="flex items-center gap-2">
              <!-- Prev -->
              <button
                @click="navLightbox(-1)"
                class="w-7 h-7 flex items-center justify-center border border-zinc-200 dark:border-zinc-800 text-zinc-500 hover:border-zinc-900 dark:hover:border-zinc-100 hover:text-zinc-900 dark:hover:text-zinc-100 transition-colors"
              >
                <svg class="w-3.5 h-3.5" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"><path d="M10 3L5 8l5 5"/></svg>
              </button>
              <!-- Next -->
              <button
                @click="navLightbox(1)"
                class="w-7 h-7 flex items-center justify-center border border-zinc-200 dark:border-zinc-800 text-zinc-500 hover:border-zinc-900 dark:hover:border-zinc-100 hover:text-zinc-900 dark:hover:text-zinc-100 transition-colors"
              >
                <svg class="w-3.5 h-3.5" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"><path d="M6 3l5 5-5 5"/></svg>
              </button>
              <!-- Close -->
              <button
                @click="closeLightbox"
                class="w-7 h-7 flex items-center justify-center border border-zinc-200 dark:border-zinc-800 text-zinc-500 hover:border-zinc-900 dark:hover:border-zinc-100 hover:text-zinc-900 dark:hover:text-zinc-100 transition-colors ml-2"
              >
                <svg class="w-3.5 h-3.5" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"><path d="M3 3l10 10M13 3L3 13"/></svg>
              </button>
            </div>
          </div>

          <!-- Lightbox image -->
          <div class="flex-1 min-h-0 flex items-center justify-center p-8 overflow-hidden">
            <img
              :src="lightbox.src"
              :alt="lightbox.alt"
              class="max-w-full max-h-full object-contain"
            />
          </div>

          <!-- Lightbox meta footer -->
          <div class="border-t border-zinc-200 dark:border-zinc-800 px-6 py-4 flex items-center justify-between shrink-0">
            <div class="flex items-center gap-6">
              <div>
                <p class="text-[10px] font-medium tracking-[0.1em] uppercase text-zinc-400 dark:text-zinc-600 mb-0.5">Judul</p>
                <p class="text-[13px] font-medium text-zinc-900 dark:text-zinc-100">{{ lightbox.title }}</p>
              </div>
              <div>
                <p class="text-[10px] font-medium tracking-[0.1em] uppercase text-zinc-400 dark:text-zinc-600 mb-0.5">Kategori</p>
                <p class="text-[13px] text-zinc-700 dark:text-zinc-300">{{ lightbox.category }}</p>
              </div>
              <div>
                <p class="text-[10px] font-medium tracking-[0.1em] uppercase text-zinc-400 dark:text-zinc-600 mb-0.5">Tahun</p>
                <p class="text-[13px] text-zinc-700 dark:text-zinc-300">{{ lightbox.year }}</p>
              </div>
            </div>
            <span class="text-[11px] text-zinc-300 dark:text-zinc-700 tabular-nums">
              {{ currentLbIndex + 1 }} / {{ filteredImages.length }}
            </span>
          </div>
        </div>
      </Transition>
    </Teleport>

  </div>
</template>

<script lang="ts" setup>
import { ref, computed, nextTick } from 'vue'

useSeoMeta({
  title: 'Galeri — Dokumentasi Visual Proyek & Event NLFTs',
  ogTitle: 'Galeri — Dokumentasi Visual Proyek & Event NLFTs',
  description: 'Galeri foto dan visual dokumentasi proyek, UI design, event meetup, dan behind the scenes komunitas developer NLFTs Indonesia.',
  ogDescription: 'Dokumentasi visual NLFTs: proyek, UI design, event meetup, dan momen behind the scenes komunitas developer Indonesia.',
  ogImage: 'https://nlfts.dev/og/gallery.png',
  ogImageWidth: 1200,
  ogImageHeight: 630,
  ogImageType: 'image/png',
  ogUrl: 'https://nlfts.dev/galeri',
  ogType: 'website',
  twitterCard: 'summary_large_image',
  twitterTitle: 'Galeri NLFTs — Dokumentasi Visual Komunitas Developer Indonesia',
  twitterDescription: 'Foto proyek, event, dan behind the scenes komunitas NLFTs.',
  twitterImage: 'https://nlfts.dev/og/gallery.png',
})

// ── Filters ───────────────────────────────────────────
const filters = [
  { key: 'all',       label: 'Semua' },
  { key: 'project',   label: 'Proyek' },
  { key: 'ui',        label: 'UI Design' },
  { key: 'event',     label: 'Event' },
  { key: 'behind',    label: 'Behind the scenes' },
]

const activeFilter = ref('all')

// ── Images data ───────────────────────────────────────
// Ganti `src` dengan path gambar asli dari project kamu.
// `ratio` mengontrol tinggi gambar — gunakan format "lebar/tinggi" (CSS aspect-ratio).
interface GalleryImage {
  id: number
  src: string
  alt: string
  title: string
  category: string
  categoryKey: string
  year: string
  ratio: string
}

const images = ref<GalleryImage[]>([
  {
    id: 1,
    src: 'https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?w=800&q=80',
    alt: 'Tampilan UI dashboard NLFTs v2',
    title: 'Dashboard v2',
    category: 'UI Design',
    categoryKey: 'ui',
    year: '2025',
    ratio: '4/3',
  },
  {
    id: 2,
    src: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800&q=80',
    alt: 'Proses coding proyek internal NLFTs',
    title: 'Dev Session #12',
    category: 'Behind the scenes',
    categoryKey: 'behind',
    year: '2025',
    ratio: '16/10',
  },
  {
    id: 3,
    src: 'https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?w=800&q=80',
    alt: 'Event meetup komunitas NLFTs pertama',
    title: 'NLFTs Meetup #1',
    category: 'Event',
    categoryKey: 'event',
    year: '2024',
    ratio: '3/2',
  },
  {
    id: 4,
    src: 'https://images.unsplash.com/photo-1561070791-2526d30994b5?w=800&q=80',
    alt: 'Landing page desain korporat',
    title: 'Corporate Landing',
    category: 'UI Design',
    categoryKey: 'ui',
    year: '2025',
    ratio: '1/1',
  },
  {
    id: 5,
    src: 'https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=800&q=80',
    alt: 'Tampilan mobile app proyek klien',
    title: 'Mobile App Client',
    category: 'Proyek',
    categoryKey: 'project',
    year: '2025',
    ratio: '9/16',
  },
  {
    id: 6,
    src: 'https://images.unsplash.com/photo-1531297484001-80022131f5a1?w=800&q=80',
    alt: 'Setup workstation tim NLFTs',
    title: 'Studio Setup',
    category: 'Behind the scenes',
    categoryKey: 'behind',
    year: '2024',
    ratio: '3/2',
  },
  {
    id: 7,
    src: 'https://images.unsplash.com/photo-1573164713988-8665fc963095?w=800&q=80',
    alt: 'Workshop desain bersama komunitas',
    title: 'Design Workshop',
    category: 'Event',
    categoryKey: 'event',
    year: '2024',
    ratio: '4/3',
  },
  {
    id: 8,
    src: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800&q=80',
    alt: 'Analitik proyek SaaS NLFTs',
    title: 'SaaS Analytics',
    category: 'Proyek',
    categoryKey: 'project',
    year: '2025',
    ratio: '16/9',
  },
  {
    id: 9,
    src: 'https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?w=800&q=80',
    alt: 'Wireframe proyek e-commerce klien',
    title: 'E-Commerce Wireframe',
    category: 'UI Design',
    categoryKey: 'ui',
    year: '2024',
    ratio: '4/3',
  },
  {
    id: 10,
    src: 'https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=800&q=80',
    alt: 'Sesi live coding NLFTs stream',
    title: 'Live Coding Stream',
    category: 'Behind the scenes',
    categoryKey: 'behind',
    year: '2025',
    ratio: '16/9',
  },
  {
    id: 11,
    src: 'https://images.unsplash.com/photo-1551650975-87deedd944c3?w=800&q=80',
    alt: 'Aplikasi mobile komponen sistem',
    title: 'Component System',
    category: 'Proyek',
    categoryKey: 'project',
    year: '2025',
    ratio: '9/16',
  },
  {
    id: 12,
    src: 'https://images.unsplash.com/photo-1540575467063-178a50c2df87?w=800&q=80',
    alt: 'NLFTs annual gathering 2024',
    title: 'Annual Gathering',
    category: 'Event',
    categoryKey: 'event',
    year: '2024',
    ratio: '16/9',
  },
])

// ── Filter logic ──────────────────────────────────────
const filteredImages = computed(() =>
  activeFilter.value === 'all'
    ? images.value
    : images.value.filter((img) => img.categoryKey === activeFilter.value)
)

// ── Lightbox ──────────────────────────────────────────
const lightbox = ref<GalleryImage | null>(null)
const lbEl = ref<HTMLElement | null>(null)

const currentLbIndex = computed(() =>
  lightbox.value
    ? filteredImages.value.findIndex((img) => img.id === lightbox.value!.id)
    : 0
)

const openLightbox = async (img: GalleryImage) => {
  lightbox.value = img
  await nextTick()
  lbEl.value?.focus()
}

const closeLightbox = () => {
  lightbox.value = null
}

const navLightbox = (dir: 1 | -1) => {
  const list = filteredImages.value
  if (!list.length) return

  const idx = currentLbIndex.value
  const next = (idx + dir + list.length) % list.length
  const nextItem = list[next]

  if (nextItem) {
    lightbox.value = nextItem
  }
}

// Keyboard nav
onMounted(() => {
  window.addEventListener('keydown', handleKey)
})
onUnmounted(() => {
  window.removeEventListener('keydown', handleKey)
})

const handleKey = (e: KeyboardEvent) => {
  if (!lightbox.value) return
  if (e.key === 'Escape') closeLightbox()
  if (e.key === 'ArrowRight') navLightbox(1)
  if (e.key === 'ArrowLeft') navLightbox(-1)
}
</script>

<style scoped>
/* Keep this page aligned with the global typography token. */
.font-sans {
  font-family: 'Inter Tight', sans-serif;
}

/* Pastikan kolom masonry tidak ada gap di sisi dalam */
.columns-1 > figure,
.sm\:columns-2 > figure,
.lg\:columns-3 > figure {
  margin: 0;
}

/* Lightbox transition */
.lb-enter-active,
.lb-leave-active {
  transition: opacity 0.15s ease;
}
.lb-enter-from,
.lb-leave-to {
  opacity: 0;
}

/* Kolom border — baris kanan dan kiri menggunakan border-x dari container,
   border vertikal antar kolom ditangani oleh border-r pada figure */
@media (min-width: 640px) {
  .sm\:columns-2 > figure:not(:nth-child(2n)) {
    border-right: 1px solid;
  }
}
@media (min-width: 1024px) {
  .lg\:columns-3 > figure:not(:nth-child(3n)) {
    border-right: 1px solid;
  }
  .sm\:columns-2 > figure:not(:nth-child(2n)) {
    border-right: none;
  }
}

/* Border-color menyesuaikan mode */
figure {
  border-color: rgb(228, 228, 231); /* zinc-200 */
}
.dark figure {
  border-color: rgb(39, 39, 42); /* zinc-800 */
}
</style>