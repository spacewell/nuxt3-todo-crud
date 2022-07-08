<template>
  <div class="wrapper" v-on:click="(e) => onClickHandler(e, item.id)">
    <div class="item">
      <span>{{ name }}</span>
      <div class="buttons">
        <button v-on:click.stop v-on:click="myHandler">Edit</button>
        <button>Delete</button>
      </div>
    </div>
  </div>
</template>

<script setup>
  const props = defineProps({
    name: {
      type: String
    },
    item: {
      type: Object
    }
  })

  const router = useRouter()


  function onClickHandler(e, id) {
    router.push({ path: `/products/${id}`})
  }

  function myHandler() {
  }

</script>


<style scoped>

.wrapper {
  padding: 10px;
  display: flex;
  flex-direction: column;
  border-bottom: 1px solid #ddd;
}

.wrapper:last-child {
  border: none;
}

.item {
  padding: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  user-select: none;
  width: 100%;
}

.close {
  display: none;
}

.buttons {
  display: flex;
  flex-direction: row;
}

.buttons button:nth-child(1) {
  padding: 5px 15px;
  background: green;
  color: #fff;
  border: none;
  margin-right: 10px;
}

.buttons button:nth-child(2) {
  padding: 5px 15px;
  background: red;
  color: #fff;
  border: none;
}

.buttons button:nth-child(2):hover {
  background: #B60000;
}

.buttons button:nth-child(1):hover {
  background: #006C08;
}

</style>