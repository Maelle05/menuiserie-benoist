<template>
  <div class="post-blog-container">
    <ContentDoc
      :path="$route.params.slug ? `/realisations/blog/${$route.params.slug[0]}` : '/realisations/blog'"
    >
      <template #not-found>
        <div class="error">
          <h4>L'article que vous cherchez n'a pas été trouvé</h4>
          <a href="/">retour à l'accueil</a>
        </div>
      </template>
    </ContentDoc>
  </div>
</template>

<style>
div.post-blog-container{
  width: 85%;
  margin: auto;
  margin-top: 60px;
}
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

p:first-child{
  color: #951C3C;
}
</style>