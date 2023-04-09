<script>
export default {
  props: ['image', 'slug', 'title', 'price'],
};
</script>

<template>
  <NuxtLink
    :to="`/product/${slug}`"
    class="
      uk-display-block
      uk-inline-clip
      uk-transition-toggle
      uk-border-rounded
      uk-box-shadow-medium
    "
    tabIndex="0"
    :uk-tooltip="price"
  >
    <img
      class="uk-transition-scale-up uk-transition-opaque"
      :src="image.src"
      :alt="image.alt"
    />
  </NuxtLink>
</template>
