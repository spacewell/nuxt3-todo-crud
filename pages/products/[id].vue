<template>
  <div class="wrapper">
    <div class="back">
      <button @click="handleBackClick" class="button" type="button">Back</button>
    </div>
    <h3>
      Id: {{ id }}
    </h3>
    <h4>
      Name: Test
    </h4>
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {
    const route = useRoute()
    const router = useRouter()

    const handleBackClick = () => {
      router.back()
    }

    return {
      handleBackClick,
      id: route.params.id
    }
  }
})
</script>

<style lang='scss' scoped>
.wrapper {
  padding: 10px;
  border: 1px solid var(--border-color);
}

.back {
  margin-bottom: 20px;
}

.button {
  padding: 10px 15px;
  background-color: var(--button);
  border: none;
  color: var(--white-text);
  cursor: pointer;
}

.button:active {
  background: var(--button-active);
}
</style>
