<template>
  <div>
    <div class="location">
      <select name="country" id="country" v-on:change="countrybased">
        <option value="">Country List</option>
        <option value="global">Worldwide</option>
        <option
          v-for="(items, index) in countries"
          :key="index"
          :value="items.ID"
          >{{ items.Country }}</option
        >
      </select>
    </div>
    <div class="loading" v-if="loading">
      Fetching Data<br />
      <img :src="loadingImage" alt="loading" />
    </div>
    <div class="content" v-else>
      <div class="title">{{ title }}</div>
      <div class="date">{{ formatdate(dataDate) }}</div>
      <div class="block">
        <div class="cases">
          Cases
          <div class="newcases">
            <strong>New:</strong>{{ formatnumber(stat.NewConfirmed) }}
          </div>
          <div class="totalcases">
            <strong>Total:</strong>{{ formatnumber(stat.TotalConfirmed) }}
          </div>
        </div>
        <div class="cases" style="background-color:#ee9696">
          Deaths
          <div class="newcases">
            <strong>New:</strong>{{ formatnumber(stat.NewDeaths) }}
          </div>
          <div class="totalcases">
            <strong>Total:</strong>{{ formatnumber(stat.TotalDeaths) }}
          </div>
        </div>
        <div class="cases" style="background-color:#98ee98">
          Recovered
          <div class="newcases">
            <strong>New:</strong>{{ formatnumber(stat.NewRecovered) }}
          </div>
          <div class="totalcases">
            <strong>Total:</strong>{{ formatnumber(stat.TotalRecovered) }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import loading from "../assets/loading.png";
export default {
  name: "Body",
  methods: {
    covidinformation: function() {
      fetch("https://api.covid19api.com/summary").then((res) => {
        res.json().then((res) => {
          this.dataDate = res.Date;
          this.stat = res.Global;
          this.countries = res.Countries;
          this.loading = false;
          this.store = res;
        });
      });
    },
    countrybased: function() {
      this.loading = true;
      let country = document.getElementById("country");
      if (country.value == "global") {
        this.stat = this.store.Global;
        this.loading = false;
        this.title = "Global";
      } else {
        var deb = this.countries.find((index) => {
          return index.ID == country.value;
        });
        this.stat = deb;
        this.loading = false;
        this.title = deb.Country;
      }
    },
    formatnumber: function(num) {
      return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
    formatdate: function(date) {
      date = new Date(date);
      date = date.toLocaleString("En-IN");
      return date;
    },
  },
  data() {
    return {
      loading: true,
      title: "Global",
      dataDate: "",
      stat: null,
      countries: null,
      loadingImage: loading,
      store: [],
    };
  },
  mounted() {
    this.covidinformation();
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
  height: 30px;
  text-align: center;
  font-size: 15px;
  border: 2px solid rgb(192, 191, 191);
  border-radius: 5px;
  outline: none;
}
.location > *:focus {
  border: 2px solid black;
}
.time {
  display: block;
  text-align: center;
  color: #856b06;
  font-size: 18px;
  font-family: "Padauk", sans-serif;
}
.time > span {
  color: cadetblue;
  font-size: 20px;
  font-weight: 700;
  font-family: "Mate SC", serif;
}
.loading {
  display: block;
  text-align: center;
  margin-top: 3rem;
  font-size: 2rem;
  color: #960d41;
}
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.content > .title {
  color: cornflowerblue;
  font-family: "Mate SC", serif;
  font-size: 40px;
  font-weight: 800;
  margin: 10px auto;
}
.content > .date {
  color: darkgoldenrod;
  font-family: "Padauk", sans-serif;
  font-size: 20px;
}
.block {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.cases {
  background: rgb(212, 212, 245);
  padding: 20px 50px;
  border-radius: 10px;
  font-family: "Mate SC", serif;
  font-size: 40px;
  display: block;
  text-align: center;
  margin: 20px 20px;
  width: 270px;
}
.cases > .newcases {
  font-family: "Padauk", sans-serif;
  font-size: 20px;
}
.cases > .totalcases {
  font-family: "Padauk", sans-serif;
  font-size: 20px;
}
</style>
