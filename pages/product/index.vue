<script setup>
import products from "../../content/products.json";

const title = "Product";
const categories = [...new Set(products.map((item) => item.category))];
const category = ref('')

</script>

<template>

  <ul class="divide-x-2 flex flex-wrap justify-center mb-4 lg:mb-8">
    <li class="">
      <button
        :class="`inline-block px-4 py-2 text-yellow-800 ${category == '' ? 'font-semibold' : ''}`"
        @click="() => {
          category = ''
        }"
      >
        All
      </button>
    </li>
    <li v-for="(value,index) in categories" :key="`category-${index}`" class="">
      <button
        :class="`inline-block px-4 py-2 text-yellow-800 ${category == value ? 'font-semibold' : ''}`"
        @click="() => {
          category = value;
        }"
      >
        {{value}}
      </button>
    </li>
  </ul>

  <div class="sm:columns-2 md:columns-3 lg:columns-4">
    <div v-for="(item,index) in products.filter((item) => {
      if (category == '') {
        return true;
      }
      return item.category == category;
    })" :key="`product-${index}`" class="mb-4">
      <Product 
        :description="item.description"
        :image="item.image"
        :slug="item.slug"
        :price="item.price"
        :title="item.title"
      />
    </div>
  </div>

</template>
