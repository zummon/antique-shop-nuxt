<script setup>
import data from '../content/products.json';

const products = data.slice(0, 4);
</script>
<template>
  <div>
    <div class="uk-column-1-2@m uk-column-divider uk-padding">
      <h1>Home</h1>
      <p>Lorem, ipsum dolor.</p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo,
        libero alias beatae praesentium debitis laborum hic consequatur magni
        esse distinctio cupiditate eaque tenetur sint, rerum reprehenderit dicta
        totam. Minus, eius.
      </p>
      <ul>
        <li>Dolorum.</li>
        <li>Praesentium est quasi qui.</li>
        <li>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
      </ul>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo,
        libero alias beatae praesentium debitis laborum hic consequatur magni
        esse distinctio cupiditate eaque tenetur sint, rerum reprehenderit dicta
        totam. Minus, eius.
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo,
        libero alias beatae praesentium debitis laborum hic consequatur magni
        esse distinctio cupiditate eaque tenetur sint, rerum reprehenderit dicta
        totam. Minus, eius.
      </p>
    </div>
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
          v-for="(
            { description, image, slug, price, title }, index
          ) in products"
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
  </div>
</template>
