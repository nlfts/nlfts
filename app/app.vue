<script setup lang="ts">
import { onMounted } from 'vue'

const colorMode = useColorMode()
const route = useRoute()

const color = computed(() => colorMode.value === 'dark' ? '#09090b' : 'white')
const canonicalUrl = computed(() => `https://NLFTs.dev${route.path}`)

useHead(() => ({
  meta: [
    { charset: 'utf-8' },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
    { key: 'theme-color', name: 'theme-color', content: color.value },
    { name: 'application-name', content: 'NLFTs' },
    { name: 'author', content: 'NLFTs' },
    { name: 'robots', content: 'index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1' },

    // ── TrapStack: Meta signatures ───────────────────────────────────────
    { name: 'generator', content: 'WordPress 6.4.3' },
    { name: 'google-site-verification', content: 'trapstack-ga-verification-fake' },
    { name: 'docsearch:language', content: 'id' },
    { name: 'docsearch:version', content: '1.0.0' },
    { name: 'twikoo:version', content: '1.6.22' },
  ],

  link: [
    { rel: 'icon', type: 'image/png', href: '/nlfts.webp' },
    { rel: 'canonical', href: canonicalUrl.value },
    // Preconnect to font origins for faster discovery
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: '' },
    // Google Fonts — non-render-blocking (media=print swap trick)
    { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Inter+Tight:wght@400&display=swap', media: 'print', onload: "this.media='all'" },
    // RSS feeds
    { rel: 'alternate', type: 'application/rss+xml', title: 'NLFTs Blog RSS', href: 'https://NLFTs.dev/rss.xml' },
    { rel: 'alternate', type: 'application/atom+xml', title: 'NLFTs Blog Atom', href: 'https://NLFTs.dev/atom.xml' },
    // Algolia DocSearch CSS signature (TrapStack) — loaded async, non-blocking
    { rel: 'preload', as: 'style', href: 'https://cdn.jsdelivr.net/npm/@docsearch/css@3/dist/style.css', onload: "this.rel='stylesheet'", 'data-trapstack': 'algolia' }
  ],

  script: [
    // ── JSON-LD: Organization structured data ────────────────────────────
    {
      type: 'application/ld+json',
      innerHTML: JSON.stringify({
        '@context': 'https://schema.org',
        '@type': 'Organization',
        name: 'NLFTs',
        url: 'https://NLFTs.dev',
        logo: 'https://NLFTs.dev/nlfts.webp',
        description: 'Jasa pembuatan website, hosting, domain, game server, dan aplikasi Android di Semarang, Indonesia.',
        address: {
          '@type': 'PostalAddress',
          addressLocality: 'Semarang',
          addressRegion: 'Jawa Tengah',
          addressCountry: 'ID'
        },
        contactPoint: {
          '@type': 'ContactPoint',
          telephone: '+62-831-6032-5595',
          contactType: 'customer service',
          availableLanguage: 'Indonesian'
        },
        sameAs: [
          'https://www.instagram.com/nlfts.dev',
          'https://github.com/NLFTs',
          'https://www.tiktok.com/@webcraftidng'
        ]
      })
    },

    // ── JSON-LD: WebSite + SearchAction (sitelinks searchbox) ────────────
    {
      type: 'application/ld+json',
      innerHTML: JSON.stringify({
        '@context': 'https://schema.org',
        '@type': 'WebSite',
        name: 'NLFTs',
        url: 'https://NLFTs.dev',
        potentialAction: {
          '@type': 'SearchAction',
          target: {
            '@type': 'EntryPoint',
            urlTemplate: 'https://NLFTs.dev/docs/getting-started?q={search_term_string}'
          },
          'query-input': 'required name=search_term_string'
        }
      })
    },

    // ── TrapStack: window signatures ─────────────────────────────────────
    {
      innerHTML: `
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'G-TRAPSTACK00');
        window.anime = { version: '3.2.2', running: [], speed: 1 };
        if(!window.gsap){ window.gsap = { version: '3.12.5' }; }
        if(!window.ScrollTrigger){ window.ScrollTrigger = { version: '3.12.5' }; }
        window.ng = { version: { full: '17.3.12', major: 17 }, probe: function(){} };
        window.getAllAngularRootElements = function(){ return []; };
        window.Prism = { version: '1.29.0', languages: { javascript: true, typescript: true } };
        window.__ALGOLIA__ = { version: '4.22.1', appId: 'TRAPSTACK' };
        window.docsearch = function(cfg){ return { destroy: function(){} }; };
        window.twikoo = { version: '1.6.22', init: function(cfg){ return Promise.resolve(); } };
        window.kofiWidgetOverlay = { draw: function(name, cfg){ return true; }, 'close': function(){} };
        window.BMC = { version: '1.0.0', open: function(){}, close: function(){} };
      `,
      type: 'text/javascript'
    },

    // ── TrapStack: GA4 script src ─────────────────────────────────────────
    {
      src: 'https://www.googletagmanager.com/gtag/js?id=G-TRAPSTACK00',
      async: true,
      'data-trapstack': 'google-analytics'
    }
  ],

  htmlAttrs: {
    lang: 'id',
    'ng-version': '17.3.12'
  }
}))

useSeoMeta({
  titleTemplate: '%s - NLFTs',
  ogSiteName: 'NLFTs',
  ogImage: 'https://nlfts.dev/og/main.png',
  ogImageWidth: 1200,
  ogImageHeight: 630,
  ogImageType: 'image/png',
  twitterCard: 'summary_large_image',
  twitterSite: '@nlfts_dev',
  twitterImage: 'https://nlfts.dev/og/main.png'
})

const { data: navigation } = await useAsyncData('navigation', () => queryCollectionNavigation('docs'), {
  transform: data => data.find(item => item.path === '/docs')?.children || []
})
const { data: files } = useLazyAsyncData('search', () => queryCollectionSearchSections('docs'))
const isSearchOpen = useState('search-open', () => false)

const links = [{
  label: 'Docs',
  icon: 'i-lucide-book',
  to: '/docs/getting-started'
}, {
  label: 'Pricing',
  icon: 'i-lucide-credit-card',
  to: '/pricing'
}, {
  label: 'Blog',
  icon: 'i-lucide-pencil',
  to: '/blog'
}, {
  label: 'Changelog',
  icon: 'i-lucide-history',
  to: '/changelog'
}]

provide('navigation', navigation)

// Ensure default theme is dark when the user has not explicitly chosen a preference.
// This preserves the existing toggle behavior but makes dark the initial theme.
onMounted(() => {
  try {
    const keys = ['nuxt-color-mode', 'color-mode', 'theme']
    const hasStored = keys.some(k => !!localStorage.getItem(k))
    if (!hasStored && colorMode && colorMode.value !== 'dark') {
      colorMode.value = 'dark'
    }
  } catch (e) {
    // ignore (SSR or localStorage blocked)
  }
})
</script>

<template>
  <UApp>
    <NuxtLoadingIndicator />

    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>

    <ClientOnly>
      <AppSearch 
        v-model:open="isSearchOpen" 
        :files="files || []" 
        :navigation="navigation || []"
        :links="links"
      />
    </ClientOnly>

    <!--
      ╔══════════════════════════════════════════════════════╗
      ║  TrapStack DOM Signatures — invisible to users       ║
      ║  Wappalyzer & BuiltWith scan these DOM patterns      ║
      ╚══════════════════════════════════════════════════════╝
    -->

    <!-- Algolia DocSearch trap: crawler cari div#docsearch & .DocSearch -->
    <div id="docsearch" class="DocSearch" style="display:none" aria-hidden="true" />

    <!-- Twikoo trap: crawler cari div#twikoo & data-twikoo -->
    <div id="twikoo" data-twikoo="1.6.22" style="display:none" aria-hidden="true" />

    <!-- Prism.js trap: crawler cari class="language-*" & .token -->
    <pre style="display:none" aria-hidden="true">
      <code class="language-javascript"><span class="token keyword">const</span> x <span class="token operator">=</span> <span class="token number">1</span></code>
    </pre>

    <!-- Ko-fi widget trap: crawler cari iframe src ko-fi.com & div.kofi-button -->
    <div class="kofi-button" data-kofi-color="#29abe0" style="display:none" aria-hidden="true" />

    <!-- Buy Me a Coffee trap: crawler cari .bmc-btn & data-name -->
    <a class="bmc-btn" data-name="NLFTs" href="https://buymeacoffee.com/NLFTs" style="display:none" aria-hidden="true" rel="noopener">
      <span class="bmc-btn-text">Buy me a coffee</span>
    </a>

    <!-- Angular trap: router-outlet adalah signature Angular -->
    <div style="display:none" aria-hidden="true">
      <app-root _nghost-NLFTs-c1="" ng-version="17.3.12" />
    </div>

  </UApp>
</template>
