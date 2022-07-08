<template>
  <div>
    <TheNavigation />
    <div class="main-container">
      <NuxtPage />
    </div>
  </div>
</template>

<style>
*, *::before, *::after {
  padding: 0px;
  margin: 0px;
  box-sizing: border-box;
}

.main-container {
  width: 700px;
  margin: 20px auto;
}
</style>
