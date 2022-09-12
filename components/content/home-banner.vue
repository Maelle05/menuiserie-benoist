<template>
  <div class="home-banner">
    <slot name="bg-image" />
    <div class="home-banner__filtre"></div>
    <slot />
  </div>
</template>

<style>
.home-banner{
  width: 100%;
  height: 65vh;
  overflow: hidden;
  position: relative;
}

.home-banner img{
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
}

.home-banner__filtre{
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: #FFFFFF;
  opacity: 0.7;
}

.home-banner h1{
  color: #FFFFFF;
  position: absolute;
  font-family: 'Roboto', sans-serif;
  font-weight: 500;
  font-size: 80px;
  left: calc(50% - 345px);
  margin: 140px 0 0 0;
}
</style>