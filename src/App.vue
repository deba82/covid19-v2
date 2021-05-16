<template>
<div>
<Home props="You are  good boy"/>
<p>I am good boy</p>
</div>
</template>

<script>
import Home from './components/Home'
export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin:0;
  padding:0;
  box-sizing: border-box;
}
p{
  color:red;
}
</style>
