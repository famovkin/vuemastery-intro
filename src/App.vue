<template>
    <my-header title="Vue mastery"></my-header>
    <div class="app__container">
      <div class="app__cart">Cart({{ cart }})</div>
      <my-product
        :title="product"
        :desc="description"
        :image="imageFile"
        :stock="inStock"
        :sale="onSale"
        :details="details"
        :variants="variants"
        @add-to-cart="updateCart"
        @update-variant="updateVariant"
      />
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MyHeader from '@/components/MyHeader.vue';
import MyProduct from '@/components/ui/MyProduct.vue';

export default defineComponent({
  name: 'App',
  components: {
    MyHeader,
    MyProduct,
  },
  data: () => ({
    cart: 0,
    product: 'Socks',
    description: 'This socks are made with premium cotton to keep your feet comfortable, while an arch band provides a supportive fit with less slippage.',
    selectedVariant: 0,
    onSale: false,
    details: ['50% cotton', '30% wool', '20% polyester'],
    variants: [
      {
        id: 2234,
        color: 'green',
        image: 'socks_green.jpeg',
        quantity: 50,
      },
      {
        id: 2235,
        color: 'blue',
        image: 'socks_blue.jpeg',
        quantity: 0,
      },
    ],
  }),
  methods: {
    updateCart(): void {
      this.cart += 1;
    },
    updateVariant(index: number): void {
      this.selectedVariant = index;
    },
  },
  computed: {
    imageFile() {
      return this.variants[this.selectedVariant].image;
    },
    inStock() {
      return !!this.variants[this.selectedVariant].quantity;
    },
  },
});
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  min-width: 320px;
  background: $background;
}

.app__container {
  padding: 0px 40px;

  @media (max-width: 425px) {
    padding: 0px 10px;
  }
}

.app__cart {
  border: 1px solid $gray;
  background-color: $white;
  text-align: center;
  max-width: 100px;
  padding: 10px;
  margin-bottom: 20px;
  margin-left: auto;
  -webkit-box-shadow: 2px 2px 15px rgb(0, 0, 0, 0.27);
  -moz-box-shadow: 2px 2px 15px rgb(0, 0, 0, 0.27);
  box-shadow: 2px 2px 15px rgb(0, 0, 0, 0.27);
}
</style>
