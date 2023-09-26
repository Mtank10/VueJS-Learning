<template>
    <div id="testing">
        <div :class="{ red:isRed}">
         Hello! {{ name }} Testing
        </div>
         <br>
         {{ date }}
    </div>
    <div class="main">
    <input type="text" v-model="name"><br><br>
    <button @click="greet">Clear</button><br><br>
    <button @click="capitalize">Convert UpperCase</button>
    <input :checked="isRed" v-model="isRed" type="checkbox" @click="red">
    </div>
</template>

<script >
 export default {
    name:"TestComponent",
    data:function(){
        return {
            name:"shivam raj",
             date:false,
             isRed:false
        }
    },
    //  computed: {
    //     date: {
    //         set: function(newvalue) {
    //             console.log(newvalue);
    //             this.date = new Date(newvalue).getTime();
    //         },
    //         get:function(){
    //             return this.date
    //         }
    //     }
    // },
    created:function(){
        this.date = new Date().getFullYear() +'-' 
        + new Date().getMonth() + '-' + new Date().getDay()
    },
    mounted:function(){
        this.date = new Date().getFullYear() +'-' 
        + new Date().getMonth() + '-' + new Date().getDay()
    },
    // updated:function(){
    //     console.log('updated'); },
    //  unmounted:function() {
    //         console.log('destroyed')
    //         this.date=new Date();
    //     },
    methods: {
        greet:function(){
        this.name=""
      },
      capitalize:function(){
        this.name=this.name.toUpperCase()
      },  
      red:function(){
        //eslint-disable-next-line
        console.log(this.isRed);
      }
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
 .red{
    color:red
 }
 .green{
    color:green;
 }
</style>

