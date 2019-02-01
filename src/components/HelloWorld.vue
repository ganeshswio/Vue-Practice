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

 <!-- dynamic CSS -->


 <div class="">
   <h3>dynamic css  </h3>
   
   <h1> example1 </h1>
   <div  v-on:click="available=!available" v-bind:class="{available:available}">
   <span>ryu</span>
   </div>
<h2>example2</h2>
 <button v-on:click="nearby=!nearby">Toggle nearby</button>
     <button v-on:click="available=!available">Toggle available</button>
   <div v-bind:class="{compClasses}">
    
   <span>ryu</span>
   </div>
 </div>



 <!-- if & show -->
   <button v-on:click="error=!error">Error</button>
   <button v-on:click="success=!success">Sucess</button>
   <p v-if="error">there has been an error</p>
   <p v-else-if="success">Whooo , success</p>

 <p v-show="error">there has been an error</p>
   <p v-show="success">Whooo , success</p>

<!-- v-for -->

<div class="">
  <ul>
 
  <!-- <li v-for="(member)(index) in  members">{{index}} . {{member.name}}</li> -->
</ul>
</div>

<!-- refs -->

<div class="">
  <input type="text" ref="input">
     <button v-on:click="readRefs">Submit</button>
     <p>ypur fav food: {{output}}</p>
  
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
     value: 90,
     available:false,
     nearby:false,
     error:false,
     success:false,
     output:'your fav food',

     member :[
       {"name":"rajesh"},
       {"name":"vamshi"}
     ]
     
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
   },
   readRefs(){
     console.log(this.$refs.input.value);
     this.output = this.$refs.input.value;
   }
 
 },
// //  computed:{
// //     addToA(){
// //      console.log('add to A')
// //       return this.a+this.age
// //    },
// //    addToB(){
// //      console.log('add to B')
// //       return this.b+this.age
// //    }
//  }
computed:{
  compClasses(){
    return{
      available:this.available,
      nearby: this.nearby
    }
  },
  calculateTheValue(){
    return ((this.value* 10)/5);
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
.available span{
  background:green;
}
span{
  background:red;
  display: inline-block;
  padding: 10px;
  color:#fff;
  margin:10px 0;
}
.nearby span:after{
  content:"nearby";
  margin-left:10px;
}
</style>
