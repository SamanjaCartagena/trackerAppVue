<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

</script>

<template>
<div id="app2">
  <img :class="gender"  v-bind:src="picture" :alt="`${firstName} ${lastName}`"/>
  <h1>Hello {{firstName}}{{lastName}}</h1>
  <h3>Email:{{email}}</h3>
  <button v-on:click="getUser()" :class="gender">Get random user</button>
</div>
</template>


<script>
export default {
data(){
  return{
    firstName:'John',
    lastName:'Doe',
    email:'john@gmail.com',
    gender:'male',
    picture:'https://randomuser.me/api/portraits/men/10.jpg'
  }
},
methods:{
  async getUser(){
   const res = await fetch('https://randomuser.me/api')
   const {results} = await res.json()
   console.log(results)
    this.firstName=results[0].name.first
    this.lastName=results[0].name.last
    this.email=results[0].email
    this.gender=results[0].gender
    this.picture=results[0].picture.large
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
  cursor:pointer;
  display:inline-block;
  background: #333;
  color:white;
  font-size: 18px;
  border:0;
  padding: 1rem 1.5rem;
}
.male{
  border-color:steelblue;
  background-color: steelblue;
}
.female{
  border-color:pink;
  background-color: pink;
  color:#333;
}
img{
  border-radius:50%;
  border:5px #333 solid;
  margin-bottom:1rem;
}
</style>

<style>
@import './assets/base.css';


</style>
