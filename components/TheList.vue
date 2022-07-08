<template>
  <div class="list">
    <TheItem
      v-bind:key="item.name"
      v-for="item in products"
      :name="item.name"
      :item="item"
    />
  </div>
</template>

<script setup>
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
</script>


<style scoped>
.list {
  padding: 10px;
  border: 1px solid #000;
}
</style>