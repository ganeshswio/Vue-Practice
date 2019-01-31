<template>
  <div class="hello">

  <button v-on:click="add(1)">add year </button>
  <button v-on:click="sub(1)">sub year </button>
  <button v-on:click="add(10)">add 10 year </button>
  <button v-on:click="sub(10)">sub 10 year </button>
   <h1>age: {{age}}</h1>

<div class="canvas">

</div>


  </div>
 
  

</template>

<script>
export default {
  name: 'HelloWorld',
 data(){
   return{
     name:"ramesh",
     age:25
     
   }
   },
   methods:{
       add(inc){
     this.age+=inc;
   },
   sub(inc){
     this.age-=inc;
   }
 
 },
}
 
 

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.canvas{
  width: 600px;
  padding: 200px 20px;
  text-align: center;
  border: 1px solid #333;
}
</style>
