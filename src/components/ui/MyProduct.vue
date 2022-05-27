<template>
  <div class="product app__product">
    <img class="product__image" :src="require(`@/assets/images/${image}`)" :alt="title"/>
    <div class="product__information">
      <div class="product__content">
        <h2 class="product__title">{{ title }}</h2>
        <p
          class="product__subtitle"
          v-if="stock"
        >
          In Stock
        </p>
        <p
          class="product__subtitle"
          v-else
        >
          Out of Stock
        </p>
        <p
          class="product__subtitle product__subtitle_type_sale"
          v-if="sale"
        >
          On sale
        </p>
        <p class="product__description">{{ desc }}</p>
        <ul class="product__details">
          <li
            class="product__details-item"
            v-for="detail in details"
            :key="detail"
          >
            {{ detail }}
          </li>
        </ul>
        <ul class="product__colors">

          <li
            class="product__colors-item"
            v-for="variant in variants"
            :key="variant.id"
          >
            {{ variant.color }}
          </li>
        </ul>
      </div>
      <my-button>Add to cart</my-button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

import MyButton from '@/components/ui/MyButton.vue';
import Variant from '@/types/Variant';

export default defineComponent({
  components: {
    MyButton,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    desc: {
      type: String,
    },
    image: {
      type: String,
      required: true,
    },
    stock: {
      type: Boolean,
      required: true,
    },
    sale: {
      type: Boolean,
    },
    details: {
      required: true,
      type: Array as PropType<string[]>,
    },
    variants: {
      required: true,
      type: Array as PropType<Variant[]>,
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

  &__subtitle {
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 5px;
  }

  &__subtitle_type_sale {
    color: $red;
  }

  &__description {
    max-width: 500px;
    font-size: 15px;
    font-style: italic;
    margin-bottom: 10px;
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
