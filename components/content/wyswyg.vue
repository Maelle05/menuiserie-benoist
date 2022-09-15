<template>
  <div class="wyswyg">
    <slot />
  </div>
</template>

<style>
.wyswyg{
  width: 80%;
  margin: auto;
}

.wyswyg a {
  color: #951C3C;
}

.wyswyg h4 a{
  font-family: 'Roboto';
  font-size: 400;
  font-size: 20px;
  color: black;
}

.wyswyg p {
  font-family: 'Roboto';
  font-size: 300;
  font-size: 15px;
}

.wyswyg li {
  font-family: 'Roboto';
  font-size: 300;
  font-size: 15px;
}

</style>