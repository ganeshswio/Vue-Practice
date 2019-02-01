<template>
  <div class="hello">

  <button v-on:click="add(1)">add year </button>
  <button v-on:click="sub(1)">sub year </button>
  <button v-on:click="add(10)">add 10 year </button>
  <button v-on:click="sub(10)">sub 10 year </button>
   <h1>age: {{age}}</h1>


<!-- event modifiers -->

<div>
  <a v-on:click="click" href="https://google.com">hello this is me</a>
</div>

<!-- keyboard events -->
<div class="key">
  <h1>keyboard events</h1>
  <label for="Name">Name</label>
  <input type="text" v-on:keyup.enter="logName">
  <label for="">age</label>
  <input type="text" v-on:keyup.enter="logAge">
  
</div>
<!-- two way databinding  -->
  <div class="">
    <input type="text" > 
    <span>{{name}}</span>
  </div>

  <!-- computed properties -->
 <div class="key">
   <button v-on:click="a++">add to a</button>
    <button v-on:click="a--">del to a</button>
    <button v-on:click="b++">add to b</button>
    <button v-on:click="b--">del to b</button>


    <p> A - {{a}}</p>
    <p> B - {{b}}</p>
    <p>age+A ={{addToA()}}</p>
    <p>age+B ={{addToB()}}</p>

   
 </div>

  </div>
 
  

</template>

<script>
export default {
  name: 'HelloWorld',
 data(){
   return{
     name:"ramesh",
     age:25,
     x:0,
     y:0,
     name:"ganesh",
     a :0,
     b :0,
     
   }
   },
   methods:{
       add(inc){
     this.age+=inc;
   },
   sub(inc){
     this.age-=inc;
   },
   updateXY(){
     console.log(event);
   },
   click(){
     alert('u clicked me');
   },
   logName(){
     console.log("you entered the name");
   },
   logAge(){
       console.log("you entered the age");
   },
   addToA(){
     console.log('add to A')
      return this.a+this.age
   },
   addToB(){
     console.log('add to B')
      return this.b+this.age
   }
 
 },
 computed:{
    addToA(){
     console.log('add to A')
      return this.a+this.age
   },
   addToB(){
     console.log('add to B')
      return this.b+this.age
   }
 }
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
.key{
  padding:20px 0 20px 0;
}
</style>
