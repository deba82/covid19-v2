<template>
  <div>
    <div class="location">
      <input type="text" name="country" placeholder=".....Enter Country Details....." autocomplete="false" />
      <input type="text" name="state" placeholder=".....Enter State Details....." autocomplete="false" />
    </div>
  </div>
</template>
<script>
export default {
  name: "body",
  methods: {},
  data() {
    return{
      country:"India",
      place:"lifgggg"
    };
  },
};
</script>
<style scoped>
.location {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: auto;
}
.location > * {
  margin: 5px;
  height:30px;
  text-align: center;
  font-size:15px;
  border:2px solid rgb(192, 191, 191);
  border-radius:5px;
  outline:none;
}
.location>*:focus{
  border:2px solid black;
}

</style>
