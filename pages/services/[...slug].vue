<template>
  <div class="post-blog-container">
    <ContentDoc
      :path="$route.params.slug ? `/services/${$route.params.slug[0]}` : '/services'"
    >
      <template #not-found>
        <div class="error">
          <h4>Le service que vous cherchez n'a pas été trouvé</h4>
          <a href="/">retour à l'accueil</a>
        </div>
      </template>
    </ContentDoc>
    <div class="container-loader" ref="loader">
      <div class="lds-ellipsis"><div></div><div></div><div></div><div></div></div>
    </div>
    <div class="container-masonry" ref="masonry">
    </div>
  </div>
</template>

<script>
import MiniMasonry from "minimasonry";

export default{
  mounted: function(){
    this.AddImg(1)
  },
  methods: {
    AddImg(id) {
      const myImg = document.createElement('img');
      myImg.src = '/img/services/' + this.$route.params.slug[0] + '/' + id + '.jpg';

      const container = document.createElement('div')
      container.classList.add('item')
      container.appendChild(myImg)

      this.$refs.masonry.appendChild(container)

      myImg.addEventListener('error', () =>{
        this.$refs.loader.style.display = 'none';
        myImg.style.display = 'none';
        this.$refs.masonry.style.display = 'block';
        new MiniMasonry({
          container: this.$refs.masonry,
          gutterX: 10,
          gutterY: 10
        });
      });
      myImg.addEventListener('load', () =>{
        this.imageFound(id)
      });
    },
    imageFound(id){
      this.AddImg(id+1)
    },
  }
}
</script>

<style>
div.error{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

div.error h4{
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
}

div.error a{
  display: block;
  background-color: #951C3C;
  padding: 13px 30px;
  border-radius: 25px;
  color: white;
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 300;
  text-decoration: none;
}

div.error a:hover{
  background-color: #ab1e43;
}

.container-masonry{
  width: 85%;
  margin: auto;
  position: relative;
  min-height: 300px;
  margin-top: 70px ;
  display: none;
}

.container-masonry .item{
  overflow: hidden;
  position: absolute;
  border-radius: 7px;
}

.container-masonry img{
  width: 350px;
  object-fit: cover;
  transform: scale(1.05);
}

div.service-container{
  width: 85%;
  margin: auto;
  margin-top: 60px;
}

p{
  width: 85%;
  margin: auto;
  font-family: 'Roboto';
  font-size: 20px;
  text-align: center;
  margin-bottom: 16px;
}

.container-loader{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.lds-ellipsis {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-ellipsis div {
  position: absolute;
  top: 33px;
  width: 13px;
  height: 13px;
  border-radius: 50%;
  background: #ab1e43;
  animation-timing-function: cubic-bezier(0, 1, 1, 0);
}
.lds-ellipsis div:nth-child(1) {
  left: 8px;
  animation: lds-ellipsis1 0.6s infinite;
}
.lds-ellipsis div:nth-child(2) {
  left: 8px;
  animation: lds-ellipsis2 0.6s infinite;
}
.lds-ellipsis div:nth-child(3) {
  left: 32px;
  animation: lds-ellipsis2 0.6s infinite;
}
.lds-ellipsis div:nth-child(4) {
  left: 56px;
  animation: lds-ellipsis3 0.6s infinite;
}
@keyframes lds-ellipsis1 {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}
@keyframes lds-ellipsis3 {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(0);
  }
}
@keyframes lds-ellipsis2 {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(24px, 0);
  }
}
</style>