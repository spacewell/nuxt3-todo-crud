<template>
  <div class="wrapper" @click="(e) => handleItemClick(e, product.id)">
    <div class="todo-item">
      <span class="todo-item__name">{{ product.name }}</span>
      <div class="todo-item__actions">
        <button @click.stop class="todo-item__edit-btn" type="button">Edit</button>
        <button @click.stop class="todo-item__delete-btn" type="button">Delete</button>
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    product: {
      type: Object,
      default: {
        id: null,
        name: null
      }
    }
  },

  setup(props) {
    const router = useRouter()

    function handleItemClick(e, id) {
      router.push({ path: `/products/${id}`})
    }

    return {
      handleItemClick,
    }
  }
})

</script>


<style lang='scss' scoped>
.wrapper {
  padding: 10px;
  display: flex;
  flex-direction: column;
  border-bottom: 1px solid var(--grey-border);
}

.todo-item {
  padding: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  user-select: none;
  width: 100%;


  &__actions {
    display: flex;
    flex-direction: row;
  }

  &__edit-btn {
    padding: 5px 15px;
    background: var(--button);
    color: var(--white-text);
    border: none;
    margin-right: 10px;
  }

  &__delete-btn{
    padding: 5px 15px;
    background: var(--button);
    color: var(--white-text);
    border: none;
  }

  &__edit-btn:hover {
    background: var(--button-active);
  }

  &__delete-btn:hover {
    background: var(--button-active);
  }
}

.close {
  display: none;
}
</style>