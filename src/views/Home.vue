<template>
  <div class="home">
    <div class="product-cards-container">
      <ProductSummaryCard
        v-for="product in items"
        :key="product.id"
        :product="product"
        v-on:view-product="viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
import items from "../data/items";
import ProductSummaryCard from "../components/products/ProductSummaryCard";

export default {
  name: "Home",
  components: { ProductSummaryCard },
  data() {
    return {
      items: items,
      product: null,
    };
  },
  methods: {
    viewProduct(product) {
      this.product = product;

      console.log(this.product.id);
    },
  },
};
</script>

<style lang="scss" scoped>
.product-cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
