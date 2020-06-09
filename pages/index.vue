<template>
<section class="container">
  <h1>{{title}}</h1>
  <p>{{$store.state.message}}</p>
  <hr>
  <div class ="link" 
  @click.exact="$store.commit({type:'count',message:'add 1!',add:1})"
  @click.shift="$store.commit({type:'count',message:'add 5!',add:5})"
  @click.ctrl="$store.commit({type:'count',message:'add 10!',add:10})">
    <a @click.stop = "$store.commit('reset')">
      clicked:{{$store.state.counter}}
    </a>
  </div>
</section>
</template>

<script>
export default {
data:function(){
  return{
    title:'Hello',
    message:'This is message',
  };
},

methods:{
  doAction:function(){
    this.$store.state.counter++;
  }
}

};
</script>

<style>
.container {
padding: 5px 10px;
}

h1{
  font-size:60pt;
  color:#345980;
}

p{
  padding-top:5px ;
  font-size:20pt;
}
pre{
  padding: 10px;
  font-size:18pt;
  background-color: #efefef;
}

hr{
  margin:10px 0px;
}
</style>
