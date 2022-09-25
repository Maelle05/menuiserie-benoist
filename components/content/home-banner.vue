<template>
  <div class="home-banner">
    <slot name="bg-image" />
    <div class="home-banner__filtre"></div>
    <slot />
    <div class="home-banner__annim-text">
      <p>Travaux sur mesure <span> Dressing </span></p>
    </div>
  </div>
</template>

<script>
  export default {
    mounted: function() {
      this.step = 0
      this.values = ['Dressing' , 'Cuisine', 'Placards', 'Mobilier d’agencement', 'Parquet', 'Bains', 'Portes d’entrée', 'Fênetres', 'Terrasse', 'Pergolas' , 'Mobilier d’exterieur', 'Portail', 'Clôture' ]
      this.span = document.querySelector('.home-banner__annim-text span')
      this.annimText(this.step)
    },
    methods: {
      submitMessage() {
        console.log(this.socket) // something
      },
      annimText(i) {
        this.span.innerHTML = this.values[i];
        setTimeout(()=>{
          if (i < this.values.length-1) {
            this.step++
            this.annimText(this.step)
          } else {
            this.step = 0
            this.annimText(this.step)
          }
        }, 1300)
      }
    }
  }
</script>

<style>
.home-banner{
  width: 100%;
  height: 500px;
  overflow: hidden;
  position: relative;
}

.home-banner p:first-child {
  text-align: left;
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
  width: 100%;
  margin: 140px auto 0 auto;
  text-align: center;
}

.home-banner__annim-text{
  color: #FFFFFF;
  position: absolute;
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
  font-size: 36px;
  width: 100%;
  margin: 244px auto 0 auto;
  text-align: center;
  color: #000002;
}

.home-banner__annim-text p:first-child {
  text-align: center;
  margin: auto;
}

.home-banner__annim-text span {
  color: #951C3C;
}

@media only screen and (max-width : 900px){
  .home-banner{
    height: 500px;
  }

  .home-banner h1{
    font-size: 60px;
  }

  .home-banner__annim-text{
    margin: 218px auto 0 auto;
    font-size: 30px;
  }
}

@media only screen and (max-width : 517px){
  .home-banner__annim-text{
    margin: 296px auto 0 auto;
    font-size: 26px;
  }
}


@media only screen and (max-width : 312px){
  .home-banner h1{
    font-size: 40px;
  }
  
}

</style>