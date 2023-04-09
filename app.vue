<script setup>
useHead({
  // titleTemplate: (title) => (title ? title + ' - ' : '') + 'Antique Shop',
  // meta: [{ name: 'description', content: 'My amazing site.' }],
  bodyAttrs: {
    class: 'uk-background-cover uk-background-fixed uk-height-viewport',
    style:
      'background-image: url(https://source.unsplash.com/YSUnEXMVN5k/1920x2400);',
      
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
      class="
        uk-container
        uk-container-small
        uk-background-muted
        uk-border-rounded
        uk-box-shadow-large
      "
    >
      <TheHeader />
      <NuxtPage />
      <TheFooter />
    </div>
    <div class="uk-padding uk-visible@s"></div>
  </div>
</template>
