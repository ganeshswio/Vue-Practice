<template>
  <div class="hello">

  <button v-on:click="add">add year </button>
  <button v-on:click="sub">sub year </button>
   <h1>age: {{age}}</h1>
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
       add(){
     this.age++;
   },
   sub(){
     this.add;
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
</style>
