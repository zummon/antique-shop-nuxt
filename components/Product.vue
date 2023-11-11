<script>
export default {
  props: ['image', 'slug', 'title', 'price'],
};
</script>

<template>
  <abbr class="" :title="`${title} ${price}`">
    <NuxtLink
      class="flex items-center overflow-clip transition rounded shadow-md group max-h-80 md:max-h-none"
      :to="`/product/${slug}`"
    >
      <img
        class="group-hover:scale-110 group-focus:scale-110 object-cover object-center h-full w-full block transition duration-300"
        :src="image.src"
        :alt="image.alt"
      />
    </NuxtLink>
  </abbr>
</template>
