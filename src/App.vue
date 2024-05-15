 <template>
 
 <div>hello{{name}}{{age}}</div>
 <div v-html="phone"></div>
 <h2 v-bind:id="headingId">Heading</h2>
<h2 v-html="hack"></h2>
<button v-bind:disabled="isDisabled">click</button>
<h2 class="underline">Text</h2>
<h2 class="underline" v-bind:class="status">status</h2>
<h2 v-bind:class="isPromoted && 'promoted'">promoted</h2>
<h2 v-bind:class="isSoldout ? 'soldout': 'new'">soldout</h2>
<h2 v-bind:class="['new','promoted']">new promoted movie</h2>
<h2 v-bind:class="[isPromoted && 'promoted',isSolout?'soldout':'new']">Array conditional movie</h2>
<h2 v-bind:style="{color:highlightcolor}"> inlincolor</h2> 
<h2 v-if="num==0">the number is 0</h2>
<h2 v-else-if="num<0">number is negative</h2>
<h2 v-else-if="num>0">number is postive</h2>
<h2 v-else>not a number</h2>
<h2 v-if="showContentent">hello</h2>
<h2 v-for="(name,index) in names" :key="name " >{{index}} {{name}}</h2>
<h2 v-for="first in fullnames" :key='first'>{{first.first}}{{first.last}}</h2>

<div v-for="actor in actors" :key="actor.nam"><h2> Array of objects - {{actor.nam}}</h2>
<h3 v-for="movies in actor.movies" :key="movies">{{movies}}</h3></div>
<template  v-for="lis in list" :key="lis">
<h2 v-if="lis==='abc'">{{lis}}{{7+9}} </h2></template>

<template v-if="display">

  <hr><h2 >Keerthi</h2><hr>
  <h2>kavya</h2><hr></template>
 
</template>


<script>

export default {
  name: 'App',
 data(){
  return{
    name:"keerthi",
    age:"22",
    phone:"<b>12345678</b>",
    hack:'<a href ="#" onclick="alert(`hacked`)"> win a prize</a>',
    headingId:"heading",
    isDisabled:true,
    isunderline:false,
    status:'succes',
    isPromoted:true, 
    isSoldout:true,
    highlightcolor:"orange",
    stylesheet:{
      backgroundColor:"green",
      base:2
    },
  
    num:10,
    display:true,
    showContentent:true,
    names:['john','akil','trixie'],
    fullnames:[
               {first:'john',last:'doe'},
               { first:'kabir',last :'das'},
               { first:'manish',last:'sharma'},
               ],
     actors:[
      {
        nam:'jhonny',
        movies:['lucy',' dayout']

      },
      {
        nam:'jacob',
        movies:['batman','hero']
      },
      {
          nam:'nancy',
          movies:['triangle','maids']
      }
     ],
     list:['abc','bcd'] ,

method:{
  add(a){
    return a * this.base;
  }
}
    
  }  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline{
 text-decoration: underline;
}
.promoted{
  font-style:italic;
}
.new{
  color:red;

}
.soldout{
  color:green;
}
</style>