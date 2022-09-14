<template>
  <div class="card-service" ref="card" >
    <slot name="img" />
    <div class="card-service__filter" ref="filter"></div>
    <slot name="link" />
    <slot />
  </div>
</template>

<script>
  export default {
    mounted: function() {
      this.card = this.$refs.card
      this.filter = this.$refs.filter
      this.card.addEventListener('mouseover', ()=>{
        this.filter.classList.add('card-service__filter--hover')
      })
      this.card.addEventListener('mouseleave', ()=>{
        this.filter.classList.remove('card-service__filter--hover')

      })
    },
    methods: {
    }
  }
</script>

<style>
.card-service{
  width: 364px;
  height: 149px;
  background-color: #951C3C;
  margin: 5px;
  position: relative;
  overflow: hidden;
}

.card-service img{
  height: 100%;
  width: 100%;
  object-fit: cover;
  object-position: center;
  position: absolute;
  pointer-events: none;
}

.card-service__filter{
  height: 100%;
  width: 100%;
  object-fit: cover;
  object-position: center;
  position: absolute;
  background-color: #951C3C;
  opacity: 0;
  transition: opacity .3s;
}

.card-service__filter--hover{
  opacity: 0.7;
}

.card-service p{
  width: 100%;
  height: 100%;
  position: absolute;
}

.card-service p a{
  width: 100%;
  height: 100%;
  display: block;
}

.card-service p:last-child{
  position: absolute;
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 38px;
  line-height: 40px;
  color: #FFF;
  text-align: center;
  width: 100%;
  height: 100%;
  pointer-events: none;
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>