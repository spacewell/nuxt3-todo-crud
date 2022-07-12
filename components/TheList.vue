<template>
  <div class="list">
    <button class="add">Add Product</button>
    <TheItem
      v-for="product in products"
      v-bind:key="product.id"
      :product="product"
    />
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'

export default defineComponent({

  setup() {
    const products = [
      {
        id: 1,
        name: 'Item1'
      },
      {
        id: 2,
        name: 'Item2'
      }
    ]

    return { products }
  }
})
</script>


<style lang='scss' scoped>
.list {
  padding: 10px;
  border: 1px solid var(--black-border);
}

.add {
  padding: 10px 15px;
  border:none;
  color: var(--white-text);
  background: var(--button)
}

.add:active {
  background: var(--button-active)
}
</style>
