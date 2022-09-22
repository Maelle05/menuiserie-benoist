<template>
  <div>
    <ul>
      <NuxtLink v-for="{ _path: slug, title, cover, type, date } in blogPosts" :key="slug" :to="slug">
        <li >
          <img :src="cover" alt="" srcset="">
          <div class="container">
            <p>{{ title }}</p>
            <span class="date">{{date}}</span>
            <span>{{type}}</span>
          </div>
        </li>
      </NuxtLink>
    </ul>
  </div>
</template>

<script setup>
const blogPosts = await queryContent('/realisations/blog')
  .sort({ date: -1 }) // show latest articles first
  .where({ _partial: false }) // exclude the Partial files
  .find();
</script>

<style scoped>

.container{
  width:calc(100% - 45px);
  padding: 20px 25px 0 20px;
}

span{
  display: block;
  font-family: 'Roboto';
  font-size: 10px;
  color: #951C3C;
}

span.date{
  font-size: 15px;
  margin: 5px 0;
  color: black;
}

a{
  display: block;
  overflow: hidden;
  border-radius: 20px;
  text-decoration: none;
  color: black;
}

img{
  width: 100%;
  height: 100px;
  object-fit: cover;
}

ul{
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 0;
}

li{
  background-color: #F7F0EA;
  width: 100%;
  height: 200px;
  display: flex;
  flex-direction: column;
  padding-bottom: 10px;
}

p{
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
}
</style>