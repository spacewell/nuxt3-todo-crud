<template>
  <div>
    <TheNavigation />
    <div class="main-container">
      <NuxtPage />
    </div>
  </div>
</template>

<style lang='scss'>
* {
  padding: 0px;
  margin: 0px;
  box-sizing: border-box;
}

.main-container {
  max-width: 700px;
  margin: 20px auto;
}
</style>
