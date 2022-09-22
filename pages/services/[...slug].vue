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
    <div class="container-masonry" ref="masonry">
      <div class="item"><img src="/img/services/cuisines/1.jpg" alt="" srcset=""></div>
      <div class="item"><img src="/img/services/cuisines/2.png" alt="" srcset=""></div> 
      <div class="item"><img src="/img/services/cuisines/3.jpg" alt="" srcset=""></div> 
      <div class="item"><img src="/img/services/cuisines/4.jpg" alt="" srcset=""></div> 
      <div class="item"><img src="/img/services/cuisines/5.png" alt="" srcset=""></div> 
      <div class="item"><img src="/img/services/cuisines/6.jpg" alt="" srcset=""></div> 
    </div>
    {{$route.params.slug[0]}}
  </div>
</template>

<script>
import MiniMasonry from "minimasonry";

export default{
  mounted: function(){
    new MiniMasonry({
      container: this.$refs.masonry,
      gutterX: 10,
      gutterY: 10
    });
  }
}
</script>

<style>
.container-masonry{
  width: 85%;
  margin: auto;
  position: relative;
}

.container-masonry .item{
  overflow: hidden;
  position: absolute;
  border-radius: 5px;
}

.container-masonry img{
  max-width: 350px;
  object-fit: cover;
}

div.service-container{
  width: 85%;
  margin: auto;
  margin-top: 60px;
}
</style>