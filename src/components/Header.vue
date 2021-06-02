<template>
  <div>
    <h1>
      Covid 19-Tracker
      <i class="fa i-virus">
        &#xe074;
      </i>
    </h1>
    <p>
      <a href="#"
        >!!! <i class="fa i-smiley"> &#xf118; </i> Source from Covid-19 API
        <i class="fa i-smiley"> &#xf118; </i> !!!</a
      >
    </p>
  </div>
</template>
<script>
export default {
  name: "Header",
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Mate+SC&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Padauk&display=swap");
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css");
* {
  color: black;
  text-decoration: none;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
<style scoped>
h1 {
  text-align: center;
  background: chocolate;
  color: cornsilk;
  margin: 5px auto;
  padding: 5px;
  font-family: "Mate SC", serif;
}
p > a,
p {
  text-align: center;
  font-size: 1rem;
  color: blue;
  font-weight: 1000;
  border-bottom: 3px solid burlywood;
  font-family: "Padauk", sans-serif;
}
p > a:hover{
  text-decoration: underline;
}
.i-smiley {
  color: blue;
}
.i-virus {
  color: cornsilk;
}
</style>
