<script setup>
import products from '../../content/products.json';

const route = useRoute();

const { title, description, price, image } = products.find((item) => item.slug === route.params.slug);

</script>

<template>
  
  <div class="mb-4 lg:mb-8">
    <h1 class="text-4xl text-black mb-4">{{title}}</h1>
    <p class="">{{description}}</p>
  </div>

  <div class="mb-4 lg:mb-8 text-right">
    <button
      class="bg-yellow-800 text-white p-2 px-10 text-2xl rounded shadow-md text-center"
    >
      <span class="">
        Purchese
      </span>
      <hr class="opacity-50" />
      <span class="font-custom">
        {{price}}
      </span>
    </button>
  </div>

  <img class="mx-auto rounded shadow-md" 
    :src="image.src"
    :alt="image.alt"
  />

</template>
