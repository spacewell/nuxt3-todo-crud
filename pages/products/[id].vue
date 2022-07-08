<template>
  <div class="wrapper">
    <div class="back">
      <button @click="back">Back</button>
    </div>
    <h3>
      Id: {{ id }}
    </h3>
    <h4>
      Name: Test
    </h4>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'
import {ref, onMounted, defineProps } from 'vue'

export default defineComponent({
  setup() {
    const route = useRoute()
    const router = useRouter()

    const props = defineProps({
      id: {
        type: Number
      }
    })

    function back() {
      router.back()
    }

    onMounted(() => {
      console.log(route.params)
    })

    return { back, id: route.params.id}
  }
})
</script>

<style scoped>
.wrapper {
  padding: 10px;
  border: 1px solid #000;
}

.back {
  margin-bottom: 20px;
}

.back button {
  padding: 10px 15px;
  background: blue;
  border: none;
  color: #fff;
  cursor: pointer;
}

.back button:active {
  background: rgb(0, 0, 156);
}
</style>
