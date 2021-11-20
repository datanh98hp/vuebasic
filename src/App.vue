<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class="app">
    <h1>{{title}}</h1>
  </div>
  <hr/>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <Home data="Dat Anh" msg="15 Tuổi"></Home>
  <hr/>
  <DataBinding />
  <hr/>
  <!-- pass data  -->
  <!-- Activing event 'changTile' was define from ChildComponent -->
  <Child v-bind:users=users v-on:changeTitle="updateTitleText($event)" />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Home from './components/Home.vue'
import DataBinding from './components/DataBinding.vue'
import Child from './components/Child.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld, 
    Home,
    DataBinding,
    Child
  },
  data(){
    return {
      title:"Child to parent data",
      name:'Đạt',
      users:[
        {
          name:'Do Van Dat 1', email:'dat198hp@gmail.com'
        },
        {
          name:'Do Van Dat 2', email:'dat198hp@gmail.com'
        },
        {
          name:'Do Van Dat 3', email:'dat198hp@gmail.com'
        },
        {
          name:'Do Van Dat 4', email:'dat198hp@gmail.com'
        }
      ]
    }
  },
  methods:{
    updateTitleText(title){
      this.title = title
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
