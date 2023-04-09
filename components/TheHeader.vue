<template>
  <div>
    <h2 class="uk-margin-top uk-text-muted uk-text-center">Antique Shop</h2>
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
</template>
