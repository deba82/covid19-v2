<template>
  <div>
    <Header />
    <Body />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";
import Body from "./components/Body";
export default {
  name: "App",
  components: {
    Header,
    Footer,
    Body,
  },
};
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
p {
  color: red;
}
</style>
