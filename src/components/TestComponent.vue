<template>
    <div id="testing">
         Hello! {{ name }} Testing
    </div>
    <div class="main">
    <input type="text" v-model="name"><br><br>
    <button v-on:click="greet">Clear</button><br><br>
    <button v-on:click="capitalize">Convert UpperCase</button>
    </div>
</template>

<script>
 export default {
    name:"TestComponent",
    data:()=>{
        return {
            name:"shivam raj"
        }
    },
    created:function(){
        console.log('created');
    },
    mounted:function(){
        console.log('mounted');
    },
    updated:function(){
        console.log('updated'); },
        unmounted:function() {
            console.log('destroyed')
        },
    methods: {
        greet:function(){
        this.name=""
      },
      capitalize:function(){
        this.name=this.name.toUpperCase()
      },  
    },
 }
</script>
<style>
 #testing{
    font-size: 4em;
    text-align: center;
 }
 .main{
    margin: 100px;
    text-align: center;
 }
</style>

