<template>
  <div class="form">
    <div class="back">
      <button @click="backHandler">Back</button>
    </div>

    <h1>{{ title }} product</h1>
    
    <div>
      <input type="text" alt="" class="input"/>
    </div>
    <div class="save">
      <button v-on:click="saveHandler">Save</button>
    </div>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  setup() {

    const route = useRoute();
    const router= useRouter();

    const title = ref('')

    onMounted(() => {
      if(route.params.type === 'edit') {
        title.value = 'Edit'
      } else {
        title.value = 'Add'
      }
    })

    const saveHandler = () => {
      console.log(route.params)
    }

    const backHandler = () => {
      router.back()
    }

    return { saveHandler, backHandler, title }
  },
})
</script>


<style scoped>
.form {
  display: flex;
  flex-direction: column;
}

.input{
  width: 100%;
  padding: 10px;
}

div {
  margin-top: 20px;
}

button {
  padding: 10px 15px;
  background: blue;
  color: #fff;
  border: none;
}

button:active {
  
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