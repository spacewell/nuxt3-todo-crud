<template>
  <div class="form">
    <div class="back">
      <button @click="handleBackClick" type="button">Back</button>
    </div>
    <h1>{{ title }} product</h1>
    <div>
      <input type="text" alt="" class="input"/>
    </div>
    <div class="save">
      <button @click="handleSaveButtonClick" type="button">Save</button>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {
    const route = useRoute();
    const router = useRouter();

    const title = ref(null)

    onMounted(() => {
      if(route.params.type === 'edit') {
        title.value = 'Edit'
      } else {
        title.value = 'Add'
      }
    })

    // Handle, На какую кнопку ставят, событие
    const handleSaveButtonClick = () => {
      console.log(route.params)
    }

    const handleBackClick = () => {
      router.back()
    }

    return {
      handleSaveButtonClick,
      handleBackClick,
      title
    }
  },
})
</script>


<style lang='scss' scoped>
.form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  padding: 10px;
}

div {
  margin-top: 20px;
}

button {
  padding: 10px 15px;
  background: var(--button);
  color: var(--white-text);
  border: none;
}

button:active {
  background: var(--button-active);
}

.save {
  display: flex;
  justify-content: flex-end;
}

.back {
  margin: 0px;
  margin-bottom: 20px;
}
</style>