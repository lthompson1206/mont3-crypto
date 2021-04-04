<template>
  <div id="about">
    <h1>{{ msg }}</h1>
    <div v-for="(currency, index) in info" class="currency" :key="index">
      {{ currency.description }}:
      <span class="lighten">
        <span v-html="currency.symbol"></span
        >{{ currency.rate_float | currencydecimal }}
      </span>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "EventCard",
  data() {
    return {
      info: null,
      loading: true,
      errored: false
    };
  },
  filters: {
    currencydecimal(value) {
      return value.toFixed(2);
    }
  },
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => (this.info = response.data.bpi));
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.currency {
  padding: auto;
  margin-right: 140px;
  margin-left: 140px;
  background-color: #72be98;
  font-weight: bold;
  color: white;
}
h1 {
  margin-right: 140px;
  margin-left: 140px;
  background-color: #72be98;
  color: white;
  font-weight: bold;
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
</style>
