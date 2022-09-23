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
    <footer>
      <div class="footer__head">
        <div class="footer__head__text">
          <a href="mailto:b.rabouan@menuiserie-benoist.com">b.rabouan@menuiserie-benoist.com</a> 
          <a href="https://www.google.com/maps/place/Menuiserie+Benoist/@47.4414983,-0.4921559,15z/data=!4m5!3m4!1s0x0:0x1361a299b1f5e68f!8m2!3d47.4414983!4d-0.4921559" target="_blank" rel="noopener noreferrer">65 Imp. Jean Jaurès, 49800 Trélazé</a>
          <a href="tel:+33676710044">06.76.71.00.44</a>
        </div>
        <iframe class="footer__head__map" src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d10793.937188661943!2d-0.4921559!3d47.4414983!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x1361a299b1f5e68f!2sMenuiserie%20Benoist!5e0!3m2!1sfr!2sfr!4v1663172535206!5m2!1sfr!2sfr" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
      <div class="footer__main">
        <ul class="footer__main__menu">
          <li><a href="/about-contact">Contact</a></li>
          <li><a href="/mensions-legales">Mensions legales</a></li>
        </ul>
        <div class="footer__main__center">
          <a href="/"><img class="header_logo" src="/img/logo.png" alt="" srcset=""></a>
          <p>Menuiserie Benoist</p>
          <p>© Menuiserie Benoist <span ref="date">2022</span> - All right reserved</p>
        </div>
        <div class="footer__main__me">
          <a href="https://maellerabouan.com/" target="_blank">Maëlle Rabouan</a>
          <span>design & developpement</span>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
    mounted: function() {
      var date = new Date()
      this.$refs.date.innerHTML = date.getFullYear()
    },
    methods: {
      toggleMenu() {
        document.querySelector('.header_hamburger').classList.toggle('open')
        document.querySelector('.header_menu').classList.toggle('header_menu--open')
      }
    }
  }
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');

body {
  margin: 0;
}

html, body {
    max-width: 100%;
    height: 100%;
    overflow-x: hidden;
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
  box-shadow: 0px 4px 33px rgba(0, 0, 0, 0.17);
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

/* Footer */
.footer__head{
  margin-top: 70px ;
  display: flex;
  flex-direction: row;
  background-color: #F7F0EA;
  height: 259px;
}

.footer__head__text {
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.footer__head__text a {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 38px;
  color: #000000;
  text-decoration: none;
}

.footer__head__text a:last-child {
  color: #951C3C;
  text-decoration: inherit;
}

.footer__head__map {
  height: 100%;
  width: 50%;
}

.footer__main{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: end;
  margin: 60px 37px;
}

.footer__main__menu{
  list-style: none;
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 18px;
}

.footer__main__menu a {
  color: #000000;
}

.footer__main__center{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.footer__main__center p {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 28px;
}

.footer__main__center p:last-child {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 18px;
}

.footer__main__me{
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 18px;
}

.footer__main__me a{
  color: #951C3C;
  text-align: right;
  display: block;
}

@media only screen and (max-width : 1024px) {
  .footer__head{
    flex-direction: column;
    height: 300px;
  }

  .footer__head__text {
    width: 100%;
    margin: 20px 0;
  }

  .footer__head__map {
    width: 100%;
  }
}

@media only screen and (max-width : 770px) {
  .footer__main{
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
  }

  .footer__main__menu {
    padding: 0;
    transform: translateY(-20px);
  }

  .footer__main__me{
    transform: translateY(25px);
  }

  .footer__main__me a{
    text-align: center;
  }
}

@media only screen and (max-width : 380px) {
  .footer__head__text a{
    font-size: 13px;
    line-height: 18px;
  }
}

/* Base */
h2{
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 50px;
  line-height: 59px;
  text-align: center;
  margin-top: 60px;
  margin-left: 20px;
  margin-right: 20px;
}

h2 a {
  text-decoration: none;
  color: #000000;
}

h3 {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 300;
  font-size: 30px;
  line-height: 39px;
  text-align: center;
  width: 85%;
  margin: auto;
  margin-top: 0;
  margin-bottom: 44px;
}


h3 a {
  text-decoration: none;
  color: #000000;
}

@media only screen and (max-width : 1024px) {
  h2{
    font-size: 40px;
    line-height: 49px;
  }
}
</style>
