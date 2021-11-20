<template>
   <div>
        <h1>Child component </h1>
        <h2 v-for="user in users" :key="user.name">{{user.name}}</h2>
       <button v-on:click="updateTitle()">Update title</button>
   </div>
</template>
<script>
export default {
    name:'Child',
    props:['users'],

    methods:{
        updateTitle(){
            // tạo event (changeTitle) -> thay đổi giá trị bằng tham số thứ 2
            this.$emit('changeTitle','data pass from Child') 
            // 
            console.log("Update title...")
        }
    }
}
</script>