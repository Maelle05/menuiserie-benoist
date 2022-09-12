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
      <div class="header_hamburger" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
      </div>
    </header>
    <NuxtPage />
  </div>
</template>

<script setup>
const toggleMenu = (e) => {
  document.querySelector('.header_hamburger').classList.toggle('open')
  document.querySelector('.header_menu').classList.toggle('header_menu--open')
}
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
  transition-property: background-color;
}

.header_tel:hover{
  background-color: #ab1e43;
}

.header_tel img{
  margin-right: 8px;
}


.header_hamburger {
  display: none;
  width: 40px;
  height: 32px;
  position: relative;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .5s ease-in-out;
  -moz-transition: .5s ease-in-out;
  -o-transition: .5s ease-in-out;
  transition: .5s ease-in-out;
  cursor: pointer;
}

.header_hamburger span {
  display: block;
  position: absolute;
  height: 7px;
  width: 100%;
  background: #ab1e43;
  border-radius: 9px;
  opacity: 1;
  left: 0;
  -webkit-transform: rotate(0deg);
  -moz-transform: rotate(0deg);
  -o-transform: rotate(0deg);
  transform: rotate(0deg);
  -webkit-transition: .25s ease-in-out;
  -moz-transition: .25s ease-in-out;
  -o-transition: .25s ease-in-out;
  transition: .25s ease-in-out;
}

/* Hamburger */

.header_hamburger span:nth-child(1) {
  top: 0px;
}

.header_hamburger span:nth-child(2),.header_hamburger span:nth-child(3) {
  top: 12px;
}

.header_hamburger span:nth-child(4) {
  top: 24px;
}

.header_hamburger.open span:nth-child(1) {
  top: 12px;
  width: 0%;
  left: 50%;
}

.header_hamburger.open span:nth-child(2) {
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -o-transform: rotate(45deg);
  transform: rotate(45deg);
}

.header_hamburger.open span:nth-child(3) {
  -webkit-transform: rotate(-45deg);
  -moz-transform: rotate(-45deg);
  -o-transform: rotate(-45deg);
  transform: rotate(-45deg);
}

.header_hamburger.open span:nth-child(4) {
  top: 18px;
  width: 0%;
  left: 50%;
}


@media only screen and (max-width : 1024px) {
  .header_menu {
    position: absolute;
    top: 80px;
    left: 0;
    background-color: #FEFCFC;
    padding: 0;
    margin: 0;
    width: 100%;
    transform: translateX(100%) ;
    z-index: 29;
    transition: transform .3s;
  }

  .header_menu--open{
    transform: translateX(0) ;
  }

  .header_menu li{
    display: block;
    margin: 0;
    padding: 0;
  }

  .header_menu li a {
    display: block;
    padding: 30px;
    border-top: solid #951C3C;
  }

  .header_menu li:last-child {
    border-bottom: solid #951C3C;
  }

  .header_menu li:hover{
    background-color: #951c3c49;
  }

  .header_menu li a:hover{
    color: black;
  }

  .header_hamburger{
    display: block;
  }
}

@media only screen and (max-width : 380px) {
  .header_tel{
    display: none;
  }
}

</style>
