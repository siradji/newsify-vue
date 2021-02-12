<template>
  <div id="app">
    <Header />
    <main id="main">
      <Search v-on:filter="fetchArticles" />
      <div class="content">
        <Articles news="news"/>
      </div>
    </main>
  </div>
</template>

<script>
import Articles from './components/Articles.vue'
import Header from "./components/layout/Header.vue";
import Search from './components/Search.vue';

import axios from 'axios';

const BASE_URL = 
`https://api.nytimes.com/svc/mostpopular/v2/emailed/7.json?api-key=${process.env.VUE_APP_API_KEY}`;

export default {
  name: "App",
  components: {
    Header,
    Search,
    Articles
  },

  data() {
    return {
      news: [],
      loading: true
    }
  },

 async created() {
    this.news = (await axios.get(BASE_URL)).data.results;
    this.loading = false;
  },

  methods:{
    async fetchArticles(filterString) {
      const filterUrl = 
        `https://api.nytimes.com/svc/mostpopular/v2/${filterString}/7.json?api-key=${process.env.VUE_APP_API_KEY}`;
        this.loading  = true;
        this.news = (await axios.get(filterUrl)).data.results
        this.loading = false;

    }
  }

};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  background: #000;
  color: #fff;
}

.content {
  margin: 0 auto;
  max-width: 80%;
}
</style>
