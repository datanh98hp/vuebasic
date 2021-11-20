<template>
  <div>
    <h1>
      Helllo Home <span>{{ data }}</span>
    </h1>

    <h2>{{ msg }}</h2>

    <h1>
      Other name <span>{{ name }}</span>
    </h1>

    <h3 v-if="show">Show ........</h3>
    <h3 v-else>Show .......Else.</h3>

    <button v-on:click="hello(data)">Greeting</button>
    <div v-if="show">
      <button v-on:click="display()">Hide</button>
    </div>
    <div v-else>
      <button v-on:click="display()">Show</button>
    </div>
    <!-- for loop -->
    <table border="1px">
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
        </tr>
        <tr v-for="user in users" :key="user.id">
            <td>{{user.id}}</td>
            <td>{{user.name}}</td>
            <td>{{user.email}}</td>
        </tr>
    </table>
    <!-- Templete -->
    <p v-html="header"></p>
    
    <button v-on:click="clickMe" v-bind:disabled="!btnShow">Click ME</button>

    <div>
      <h2 class="vueStyle">Class binding</h2>
      <h2 v-bind:style="{color:colorName}">style binding</h2>
      <h2 v-bind:class="{display:show,vueStyle:show}">Class with Object</h2>
      <h2 v-bind:class="[checkDisplay?d : v]">Class with Array</h2>
    </div>   
  </div>
</template>

<script>
export default {
  name: "Home",
  props: {
    data: String,
    msg: String,
    
  },
  methods: {
    hello(name) {
      console.log("Hii " + name);
    },
    display() {
      this.show = !this.show;
    },
    clickMe(){
       this.name = "DA"
       this.btnShow = !this.btnShow
    }
  },
  data() {
    return {
      name:"",
      header:"<h3>Templete</h3>",
      btnShow:true,
      show: true,
      d:'display',
      v:'vueStyle',
      colorName:'skyblue',
      checkDisplay:true,
      users: [
        {
          id: 1,
          name: "Đỗ Văn Đạt",
          email: "dat98hp@gmail",
        },
        {
          id: 2,
          name: "Đặng Thanh Sơn 1",
          email: "Son98hp@gmail",
        },
        {
          id: 3,
          name: "Đặng Thanh Sơn 2",
          email: "Son98hp@gmail",
        },
        {
          id: 4,
          name: "Đặng Thanh Sơn 3",
          email: "Son98hp@gmail",
        },
      ],

    };
  },
};
</script>
<style>
.vueStyle {
  color:brown
}
.display{
  background-color:rgb(235, 96, 124) ;
}
</style>