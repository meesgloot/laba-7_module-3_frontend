<template>
  <div id="center">
    <div v-for="(item, index) in data" :key="item.id" @click="isActive[index] = !isActive[index]" class="cards" :class="{ active: isActive[index],invisible: isHidden[index] }">
      <p class="main">{{ item.name }}</p>
      <button @click="isHidden[index] = !isHidden[index]">Hidden</button>
      <img :src="item.img" alt="Movie">
      <p class="text">{{ item.text }}</p>
    </div>
  </div>
</template>

<script>
import json from './components/listMovies.json';

export default {
  data() {
    return {
      data: json,
      isActive: new Array(json.length).fill(false),
      isHidden: new Array(json.length).fill(false),
    };
  },
 
};
</script>

<style>
  .invisible {
    visibility: hidden;
  }
  button{
    border-radius: 6px;
    background-color: aqua;
    width: 100px;
    height: 60px;
    margin-bottom: 15px;
  }
  .cards.active {
    width: 400px; 
    height: auto;
  }
  .text {
    visibility: hidden;
    height: 0;
  
  }
  .cards.active .text {
    visibility: visible;
    opacity: 1;
    height: auto;
  }
  .main {
    font-size: x-large;
  }
  #center {
    text-align: center;
    min-height: 320px;
    display: flex;
    flex-wrap: wrap;
  }
  .cards {
    background-color: black;
    color: aliceblue;
    border-radius: 4px;
    width: 400px;
    height: 320px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 10px 20px;
    text-align: center;
    box-shadow: 10px 5px 5px aqua;
  }
  img{
    width: auto;
    height: 200px; 
    text-align: center;
  }
  body{
    background: url(https://catherineasquithgallery.com/uploads/posts/2023-01/1674292577_catherineasquithgallery-com-p-serie-kirpichiki-fon-foto-186.jpg) ;
    -webkit-background-size: cover;
    background-size: cover;
  }
</style>
