<script setup>
import products from '../../content/products.json';

const title = 'Product';
</script>
<template>
  <div class="uk-margin-top uk-margin-bottom">
    <div
      class="
        uk-child-width-1-2@s
        uk-child-width-1-3@m
        uk-child-width-1-4@l
        uk-grid-small
      "
      uk-grid="masonry: true"
    >
      <div
        v-for="({ description, image, slug, price, title }, index) in products"
        :key="index"
      >
        <Product
          :description="description"
          :image="image"
          :slug="slug"
          :price="price"
          :title="title"
        />
      </div>
    </div>
  </div>
</template>
