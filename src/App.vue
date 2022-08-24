<template>
  <div id="app">
    <h2>Export data to Excel example in Vue.js</h2>
    <button @click="exportData">Download file</button>
    <div class="np-credits">wwww.nightprogrammer.com</div>
  </div>
</template>

<script>
import { excelParser } from "./excel-parser";
import { sampleData } from "./sample-data";

export default {
  name: "App",
  data() {
    return {
      listData: sampleData,
    };
  },
  methods: {
    exportData() {
      excelParser().exportDataFromJSON(this.listData, null, null);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
}

button {
  background-color: #004cbe;
  color: #ffffff;
  border: 0px;
  border-radius: 6px;
  padding: 6px 20px;
  margin-right: 1em;
  cursor: pointer;
  transition: all 0.3s;
}

button:hover {
  background-color: #2f79e7;
  transition: all 0.3s;
}

.np-credits {
  font-size: 12px;
  margin-top: 12px;
  color: #4b4b4b;
}
</style>