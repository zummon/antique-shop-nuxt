<script setup>
import products from "../../content/products.json";

const title = "Product";
let categories = [...new Set(products.map((item) => item.category))];
</script>
<template>
  <div class="uk-margin-top uk-margin-bottom" uk-filter="target: .js-filter">
    <ul class="uk-subnav uk-subnav-divider uk-flex-center">
      <li class="uk-active" uk-filter-control>
        <a href="#">All</a>
      </li>
      <li
        v-for="(text, index) in categories"
        :uk-filter-control="`[data-category='${text}']`"
        :key="`category-${index}`"
      >
        <a href="#">{{ text }}</a>
      </li>
    </ul>
    <div
      class="js-filter uk-child-width-1-2@s uk-child-width-1-3@m uk-child-width-1-4@l uk-grid-small"
      uk-grid="masonry: true"
    >
      <div
        v-for="(
          { description, image, slug, price, title, category }, index
        ) in products"
        :data-category="category"
        :key="`product-${index}`"
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
