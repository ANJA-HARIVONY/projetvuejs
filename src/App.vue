<script setup>
import {ref} from "vue";

  const mane='anja harivony';
  const nomstyle= ref();
  const status= true;
  const tabcolor=['green','red','blue','cyan','yellow'];

  const i = ref(0);

  const incremente=() => {
    if (i.value<4)
    {
      i.value++;
    nomstyle.value = "color:"+tabcolor[i.value];
    //console.log(tabcolor[i.value]);
    } 
  };

  const decremente=() => {
    if(i.value>0)
    {
      i.value--;
    nomstyle.value = "color:"+tabcolor[i.value];
   // console.log(i.value);
    }
 
  };

  const reset=() => {

    i.value=0;
    nomstyle.value = "color:"+tabcolor[i.value];
  }
 
 
</script>

<template>
  <div class="positive">
    <h2 v-bind:style="nomstyle">project con vue.js avec {{mane.toUpperCase()}}</h2>
  </div>
  <div>
    <h1>{{i}}</h1>
    <ul>
      <li v-for="color,index in tabcolor">{{color}} {{index}}</li>
    </ul>
  </div>
    <button v-on:click="incremente">Incremente</button>
    <button v-on:click="decremente">Decremente</button>
    <button v-on:click="reset">Reset</button>

</template>

<style>

.positive{
  align-content: center;
}

h2{
  font-size:35px;
  font-family: Verdana, Tahoma, sans-serif, 'Times New Roman', Times, serif;

}
h3{
  background-attachment: fixed;
}

</style>