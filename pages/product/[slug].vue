<script setup>
import products from '../../content/products.json';

const route = useRoute();

const { title, description, price, image } = products.find(
  ({ slug }) => slug === route.params.slug
);
</script>
<template>
  <div class="uk-padding">
    <div class="uk-flex uk-flex-wrap">
      <div>
        <h1>{{ title }}</h1>
        <p class="uk-heading-bullet">{{ description }}</p>
      </div>
      <div class="uk-margin-auto-left uk-text-center">
        <a
          class="
            uk-button
            uk-button-primary
            uk-text-large
            uk-border-rounded
            uk-box-shadow-medium
          "
        >
          Purchese
          <hr class="uk-margin-remove" />
          {{ price }}
        </a>
      </div>
    </div>
    <img
      class="uk-align-center uk-border-rounded uk-box-shadow-medium"
      :src="image.src"
      :alt="image.alt"
    />
  </div>
</template>
