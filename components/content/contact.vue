<template>
  <div class="contact-container">
    <a href="mailto:b.rabouan@menuiserie-benoist.com">
      <img src="/img/icons/c-mail.png" alt="" srcset="">
      <span>b.rabouan@menuiserie-benoist.com</span>
    </a>
    <a href="tel:+33676710044">
      <img src="/img/icons/c-tel.png" alt="" srcset="">
      <span>06 76 71 00 44</span>
    </a>
  </div>
</template>

<style scoped>
.contact-container{
  width: 75%;
  margin: auto;
  margin-top: 65px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}

.contact-container a {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 275px;
  color: #951C3C;
  font-family: 'Roboto';
  text-align: center;
  text-decoration: none;
  transition: all .3s;
}
.contact-container a:hover img{
  transition: all .3s;
  opacity: 0.6;
}

.contact-container a img {
  width: 60px;
}

.contact-container a span {
  margin-top: 20px ;
}

@media only screen and (max-width : 580px){
  .contact-container{
    flex-direction: column;
    margin-top: 0px;
  }
  .contact-container a{
    margin-top: 40px;
  }
}
</style>