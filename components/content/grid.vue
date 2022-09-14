<template>
  <div class="grid">
    <slot />
  </div>
</template>

<style scoped>
.grid{
  width: 70%;
  margin: auto;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>