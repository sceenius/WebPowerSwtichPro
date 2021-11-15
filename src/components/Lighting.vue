<template>
  <div>
    <h1>{{ msg }}</h1>
    <h3>Prototyping the interface with the Web Power Switch Pro.</h3>
    <button v-if="lights" v-on:click="lightsOff()">
      <fa icon="coffee" /> LIGHTS OFF
    </button>
    <button v-else v-on:click="lightsOn()">
      <fa icon="coffee" /> LIGHTS ON
    </button>
  </div>
</template>

<script>
export default {
  name: "Caribbean Courtyard Villa",
  getHoursCondition: String,
  lights: false,

  props: {
    msg: String,
  },

  ///////////////////////////////////////////////////////////////////////////////
  //  DATA
  ///////////////////////////////////////////////////////////////////////////////
  data() {
    return {
      hours: new Date().getHours(),
      getHoursCondition: "", //define the variable first
      lights: false,
    };
  },

  ///////////////////////////////////////////////////////////////////////////////
  //  METHODS
  ///////////////////////////////////////////////////////////////////////////////
  methods: {
    getHours: function () {
      if (this.hours >= 5 && this.hours <= 17) {
        this.getHoursCondition = "day";
      } else {
        this.getHoursCondition = "night";
      }
    },
    lightsOn() {
      this.lights = true;
    },
    lightsOff() {
      this.lights = false;
    },
  },

  ///////////////////////////////////////////////////////////////////////////////
  //  MOUNTED
  ///////////////////////////////////////////////////////////////////////////////
  mounted() {
    this.getHours();
    document.body.className = this.getHoursCondition;
  },
};
</script>

<style>
body.night {
  background: url("https://assets.hypha.earth/images/bg_night.png") no-repeat
    center center fixed;
  background-size: cover;
  background-color: #111;
}

body.day {
  background: url("https://assets.hypha.earth/images/bg_day.png") no-repeat
    center center fixed;
  background-size: cover;
  background-color: #ddd;
}

h1 {
  font-size: 3em;
  color: #fff;
}

h3 {
  margin: -140px 0 100 0;
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

button {
  background-color: #F1C232;
  border: none;
  color: #fff;
  padding: 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 26px;
  margin: 4px 2px;
  border-radius: 15px;
}
</style>
