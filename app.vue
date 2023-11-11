<script setup>
const route = useRoute()
let sitename = 'Antique Shop'
let navs = [
		{ path: '/', text: 'Home' },
		{ path: '/about', text: 'About' },
	]
useHead({
  // titleTemplate: (title) => (title ? title + ' - ' : '') + 'Antique Shop',
  // meta: [{ name: 'description', content: 'My amazing site.' }],
});
</script>

<template>
  <div class="bg-cover bg-center bg-fixed min-h-screen lg:py-20 text-zinc-500"
    :style="{ backgroundImage: `url(https://source.unsplash.com/YSUnEXMVN5k/1920x2400)` }"
  >
    <!-- Photo by Sergey Sokolov on Unsplash 
		https://unsplash.com/photos/YSUnEXMVN5k -->
    <Head>
      <!-- need to fix for other page title -->
      <Title>{{sitename}}</Title>
      <!-- need to fix try to find a way to passing up props from pages -->
      <!-- <meta property="og:title" content={title} />
      <meta name="twitter:title" content={title} />
      <meta name="description" content={description} />
      <meta property="og:description" content={description} />
      <meta name="twitter:description" content={description} />
      <meta property="og:image" content={image.src} />
      <meta name="twitter:image" content={image.src} /> -->
      <link rel="preconnect" href="https://fonts.googleapis.com" />
      <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
      <link
        href="https://fonts.googleapis.com/css2?family=Sacramento&display=swap"
        rel="stylesheet"
      />
    </Head>
    
    <div class="max-w-5xl mx-auto bg-zinc-50 rounded shadow-lg">
      <div class="p-4 lg:p-8">
        <h2
          class="text-zinc-500 text-4xl text-center mb-4 lg:mb-8 cursor-default font-custom"
        >
          {{sitename}}
        </h2>

        <div
          class="flex flex-wrap justify-center items-baseline font-serif"
        >
          <div class="border-b-2 grow px-3 py-1 lg:px-5 lg:py-3">&nbsp;</div>
          <div v-for="(item, index) in navs" :key="`nav-${index}`"
            :class="`border-b-2 text-yellow-800 font-semibold px-3 py-1 lg:px-5 lg:py-3 ${route.path == item.path
              ? 'border-yellow-800'
              : ''}`"
          >
            <NuxtLink :to="item.path">{{item.text}}</NuxtLink>
          </div>
          
          <div
            :class="`border-b-2 text-yellow-800 font-semibold px-3 py-1 lg:px-5 lg:py-3 ${route.path.startsWith('/product')
              ? 'border-yellow-800'
              : ''}`"
          >
            <NuxtLink to="/product">Product</NuxtLink>
          </div>
          <div
            :class="`border-b-2 text-yellow-800 font-semibold px-3 py-1 lg:px-5 lg:py-3 ${route.path == '/faq'
              ? 'border-yellow-800'
              : ''}`"
          >
            <abbr class="no-underline" title="Frequently Asked Questions">
              <NuxtLink to="/faq">FAQ</NuxtLink>
            </abbr>
          </div>
          <div class="border-b-2 grow px-3 py-1 lg:px-5 lg:py-3">&nbsp;</div>
        </div>
      </div>

      <div class="p-4 lg:p-8 font-serif">
        <NuxtPage/>
      </div>

      <div class="p-4 lg:p-8 text-center">
        <span
          class="text-zinc-500 text-2xl cursor-default font-custom"
        >
          Made by zummon (Teerapat Anantarattanachai)
        </span>
      </div>
    </div>

  </div>
</template>
