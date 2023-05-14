<script setup>
import "@fontsource/sacramento";
useHead({
  // titleTemplate: (title) => (title ? title + ' - ' : '') + 'Antique Shop',
  // meta: [{ name: 'description', content: 'My amazing site.' }],
  bodyAttrs: {
    class: "uk-background-cover uk-background-fixed uk-height-viewport",
    style:
      "background-image: url(https://source.unsplash.com/YSUnEXMVN5k/1920x2400);",
  },
});
</script>

<template>
  <div>
    <Head>
      <!-- need to fix for other page title -->
      <Title>Antique Shop</Title>
      <!-- need to fix try to find a way to passing up props from pages -->
      <!-- <meta property="og:title" content={title} />
      <meta name="twitter:title" content={title} />
      <meta name="description" content={description} />
      <meta property="og:description" content={description} />
      <meta name="twitter:description" content={description} />
      <meta property="og:image" content={image.src} />
      <meta name="twitter:image" content={image.src} /> -->
      <Link
        rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/uikit@3.14.1/dist/css/uikit.min.css"
      />
      <Script
        src="https://cdn.jsdelivr.net/npm/uikit@3.14.1/dist/js/uikit.min.js"
      ></Script>
      <Script
        src="https://cdn.jsdelivr.net/npm/uikit@3.14.1/dist/js/uikit-icons.min.js"
      ></Script>
    </Head>
    <div class="uk-padding uk-visible@s"></div>
    <div
      class="uk-container uk-container-small uk-background-muted uk-border-rounded uk-box-shadow-large"
    >
      <!-- header -->
      <div>
        <h2
          class="uk-margin-top uk-text-muted uk-text-center"
          style="font-family: 'Sacramento', cursive"
        >
          Antique Shop
        </h2>
        <ul class="uk-flex-center uk-tab">
          <li :class="$route.path === '/' ? 'uk-active' : ''">
            <NuxtLink to="/"> Home </NuxtLink>
          </li>
          <li :class="$route.path === '/about' ? 'uk-active' : ''">
            <NuxtLink to="/about"> About </NuxtLink>
          </li>
          <li :class="$route.path.startsWith('/product') ? 'uk-active' : ''">
            <NuxtLink to="/product"> Product </NuxtLink>
          </li>
          <li :class="$route.path === '/faq' ? 'uk-active' : ''">
            <NuxtLink
              to="/faq"
              uk-tooltip="title: Frequently Asked Questions; pos: bottom"
            >
              FAQ
            </NuxtLink>
          </li>
        </ul>
      </div>

      <!-- body -->
      <NuxtPage />

      <!-- footer -->
      <div class="uk-text-center uk-margin-large-top uk-margin-large-bottom">
        <a
          class="uk-link-reset uk-text-large"
          href="https://zummon.page/"
          target="_blank"
          style="font-family: 'Sacramento', cursive"
        >
          Made by zummon
        </a>
      </div>
    </div>
    <div class="uk-padding uk-visible@s"></div>
  </div>
</template>
