<template>
  <div>
    <header>
      <a href="/"><img class="header_logo" src="/img/logo.png" alt="" srcset=""></a>
      <ul class="header_menu">
        <li><a href="/">Accueil</a></li>
        <li><a href="/services">Services</a></li>
        <li><a href="/realisations">Réalisations</a></li>
        <li><a href="/about-contact">Contact</a></li>
      </ul>
      <a class="header_tel" href="tel:+33676710044"><img src="/img/icons/telephone.png" alt="" srcset="">06 76 71 00 44</a>
    </header>
    <NuxtPage />
  </div>
</template>

<script>

</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');

body {
  margin: 0;
}

header{
  background-color: #FEFCFC;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: calc(100% - 60px);
  padding: 16px 30px;
  position: sticky;
  top: 0;
  font-family: 'Roboto', sans-serif;
  font-weight: 300;
  z-index: 30;
}

.header_logo{
  height: 44px;
  width: 44px;
}

.header_menu li {
  list-style: none;
  display: inline;
  margin-left: 53px;
}

.header_menu li:first-child {
  margin-left: 0;
}

.header_menu li a {
  text-decoration: none;
  color: #000000;
  transition-duration: .3s;
}

.header_menu li a:hover {
  color: #951C3C;
}

.header_tel {
  background-color: #951C3C;
  text-decoration: none;
  color: #FEFCFC;
  padding: 13px 20px 11px 20px;
  border-radius: 50px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  transition-duration: .3s;
}

.header_tel:hover{
  background-color: #ab1e43;
}

.header_tel img{
  margin-right: 8px;
}

@media only screen and (max-width : 1024px) {
  .header_menu{
    display: none;
  }
}


</style>
