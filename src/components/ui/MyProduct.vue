<template>
  <div class="product app__product">
    <img class="product__image" src="@/assets/images/socks_blue.jpeg" alt="Image"/>
    <div class="product__information">
      <div class="product__content">
        <h2 class="product__title">{{ title }}</h2>
        <p class="product__stock">In Stock</p>
        <ul class="product__details">
          <li class="product__details-item">50% cotton</li>
          <li class="product__details-item">30% wool</li>
          <li class="product__details-item">20% polyester</li>
        </ul>
        <ul class="product__colors">
          <li class="product__colors-item">green</li>
          <li class="product__colors-item">blue</li>
        </ul>
      </div>
      <my-button>Add to cart</my-button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import MyButton from '@/components/ui/MyButton.vue';

export default defineComponent({
  components: {
    MyButton,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
  },
});
</script>

<style lang ="scss">
.product {
  display: flex;
  justify-content: center;
  gap: 50px;

  &__information {
    gap: 15px;
  }

  &__title {
    font-size: 50px;
  }

  &__stock {
    font-size: 22px;
    font-weight: 700;
  }

  &__details-item {
    font-size: 18px;
  }

  &__information {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  &__image {
    align-self: center;
    width: 400px;
    height: 400px;
    object-fit: cover;
    padding: 20px;
    border: 2px solid $gray;
  }

  @media (max-width: 768px) {
    & {
      flex-direction: column;
    }

    &__information {
      width: 100%;
      flex-direction: row;
    }

    &__image {
      width: 300px;
      height: 300px;
    }

    .button {
      align-self: flex-end;
    }
  }
}

.app__product {
  margin-bottom: 40px;
}
</style>
