<template>
  <div>
    <p  v-on:mouseover="run('Debasish clicked it');superior();">Hello {{ name }} & i think your age is {{age[0]}}</p>
    <p>{{props}}</p>
  </div>
</template>
<script>
export default {
  name: "Home",
  data() {
    return { name: "Debasish",age:["25"] };
  },
  methods:{
      run(data){
          alert(data);
      },
      superior(){
          console.log("Debasish")
      }
  },
  props:{
      props:String
  }
};
</script>
<style scoped>
p{
    color:green;
}
</style>

