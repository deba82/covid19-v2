<template>
  <div class="anim"><span></span>|</div>
</template>
<script>
export default {
  name: "Footer",
  methods: {
    animate: function() {
      var i = 0;
      var txt = "This app is made by DEBASISH  ";
      var speed = 300;
      function typeWriter() {
        if (i < txt.length) {
          document.querySelector(".anim>span").innerHTML += txt.charAt(i);
          i++;
          setTimeout(typeWriter, speed);
        }
        if (i == txt.length) {
          i = 0;
          document.querySelector(".anim>span").innerHTML = "";
        }
      }
      typeWriter();
    },
  },
  mounted() {
    this.animate();
  },
};
</script>
<style scoped>
.anim,
.anim > span {
  text-align: center;
  font-family: "Padauk", sans-serif;
  font-size: 2rem;
  color: crimson;
}
</style>
