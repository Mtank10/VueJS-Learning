<template>
    <div id="testing">
         Hello! {{ name }} Testing
         <br>
         {{ date }}
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
            name:"shivam raj",
            date:false
        }
    },
    created:function(){
        console.log('created');
        this.date=new Date();
    },
    mounted:function(){
        console.log('mounted');
        this.date=new Date();
    },
    updated:function(){
        console.log('updated'); },

     unmounted:function() {
            console.log('destroyed')
            //this.date=new Date();
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
    font-size: 2em;
    text-align: center;
 }
 .main{
    margin: 100px;
    text-align: center;
 }
</style>

