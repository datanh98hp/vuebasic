<template>
    <div>
        <h1>Bind Componenet</h1>
        <h2>{{message}}</h2>
        <!-- binding with message -->
        <textarea class="message" type="text" v-model="message" />
    </div>
</template>
<script>

export default {
   name:'HomeBind',
   props:{

   } ,
   data(){
       return {
           message:"A hihihi"
       }
   }
}
</script>
<style  scoped>
    .message{
        outline-style: none;
        background-color: cornflowerblue;
    }
</style>