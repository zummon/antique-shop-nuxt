<script setup>
import data from '../content/products.json';

const products = data.slice(4, 8);
const title = 'About';
</script>
<template>
  <div>
    <div class="uk-column-1-2@m uk-column-divider uk-padding">
      <h1>{{ title }}</h1>
      <p>
        <a
          class="uk-icon-button uk-margin-small-right"
          uk-icon="facebook"
          href="#"
        ></a
        ><a
          class="uk-icon-button uk-margin-small-right"
          uk-icon="instagram"
          href="#"
        ></a
        ><a
          class="uk-icon-button uk-margin-small-right"
          uk-icon="pinterest"
          href="#"
        ></a
        ><a
          class="uk-icon-button uk-margin-small-right"
          uk-icon="twitter"
          href="#"
        ></a
        ><a
          class="uk-icon-button uk-margin-small-right"
          uk-icon="youtube"
          href="#"
        ></a>
      </p>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Odit,
        recusandae. Vitae voluptates, ad ipsam itaque qui, doloremque,
        recusandae possimus sunt exercitationem ullam harum temporibus nulla.
        Praesentium est quasi qui. Dolorum.
      </p>
      <ul>
        <li>Dolorum.</li>
        <li>Praesentium est quasi qui.</li>
      </ul>
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
