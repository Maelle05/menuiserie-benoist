<template>
  <div ref="banner" class="bannerContainer">
    <span @click="hideBanner()">X</span>
    <div class="banner" >
      <p>Menuiserie Benoist sera fermée à partir du 31/08/2023 pour une durée indéterminée.</p>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    hideBanner() {
      this.$refs.banner.classList.add('hide')
    }
  }
}
</script>

<style scoped>
.bannerContainer{
  position: absolute;
  top: calc(50% - 50px);
  width: 100%;
  z-index: 1000;
}
.banner{
  display: block;
  
  background-color: #951C3C;
  color: #FFF;
  height: 100px;
  z-index: 100;
  display: flex;
  flex-direction: column;
  justify-content: center !important;
  align-items: center !important;
  font-family: 'Roboto', sans-serif !important;
  font-size: 16px !important;
  margin: 0 !important;
  padding: 0 !important;
  text-align: center;
}

.hide{
  display: none;
}

span {
  font-family: 'Roboto', sans-serif !important;
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: #FFF;
  color: #951C3C;
  cursor: pointer;
  border-radius: 100%;
  padding: 5px 9px;
  margin-bottom: 10px;
  font-size: 13px !important;
}

p {
  margin: 0 0 0 0;
}
</style>