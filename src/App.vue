<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

</script>

<template>
<div id="app2">
  <img v-bind:src="picture" :alt="`${firstName} ${lastName}`"/>
  <h1>Hello {{firstName}}{{lastName}}</h1>
  <h3>Email:{{email}}</h3>
  <button>Get random user</button>
</div>
</template>


<script>
export default {
data(){
  return{
    firstName:'John',
    lastname:'Doe',
    email:'john@gmail.com',
    gender:'male',
    picture:'https://randomuser.me/api/portraits/men/10.jpg'
  }
}

}
</script>

<style>
#app2{
  text-align: center;
  height:900px;
  width: 100%;
  background-color: white;
  color:black;
}
button{
  background-color: black;
  color:white;
  border:1px solid white;
  padding:10px;
}
</style>

<style>
@import './assets/base.css';


</style>
