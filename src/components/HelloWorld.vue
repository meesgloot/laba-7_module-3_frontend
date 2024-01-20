<template>

  <div id="center"> 
    <div v-for="(item, index) in data" :key="item.id" @click="isActive[index] = !isActive[index]" class="cards">
     <p class="main">{{ item.name }}</p> 
     <img :src=item.img> 
     <p :class="{active: isActive[index]}" >{{ item.text }}</p> 
    </div>
  </div>
</template> 
<script> 
import json from './components/listMovies.json'
export default { 
  data(){
    return{ 
      data: json,
      isActive: new Array(json.length).fill(true)
    } 
  },
}
</script> 
<style> 
.cards.active{
  width: 400px; 
  height: auto; 
} 
.active{ 
  visibility: hidden;
 } 
.main{ 
  font-size: x-large; 
}
#center{ 
  text-align: center; 
  min-height:320px;
  display: flex; 
} 
.cards{ 
  background-color: black; 
  color:aliceblue;
  border-radius: 4px;
  width: 400px;
  height: 320px; 
  display: inline-block; 
  vertical-align: middle;
  margin: 10px 20px;
  text-align: center;
  box-shadow: 10px 5px 5px aqua; 
}