<template>
  <div id="app">
    <div id="container">
      <Header />
      <SearchBar v-on:submitted-info="getInfo" />
      <MainContent :countries=results />
      <About />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import SearchBar from './components/SearchBar.vue'
import MainContent from './components/MainContent.vue'
import About from './components/About.vue'

export default {
  name: 'app',
  components: {
    Header,
    SearchBar,
    MainContent,
    About
  },
  props: {
    
  },
  data() {
    return {
      hide: false,
      results: []
    }
  },
  methods: {
    getInfo(searchterm){
      let self = this
      console.log("The submit button was clicked!")
      console.log(searchterm)
      // console.log(self.results.length)
      

      fetch(`https://restcountries.eu/rest/v2/name/${searchterm}`)
        .then(function(response){
          console.log(response)
          return response.json();
        })
        .then(function(res){
          console.log(res)
          return self.results = res
        })
        .catch(error => console.error(error))
    },


  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  background: #339FFF;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #339FFF;
  height: 100vh;
  margin-top: 50px;
  /* text-align: center; */
  /* color: #2c3e50; */
  
}

#container {
    background: #FFF;
    max-width: 1200px;
    width: 100%;
    margin: auto
}


/* Media Queries */
/* For mobile phones: */
[class*="col-"] {
  width: 100%;
}

@media only screen and (min-width: 600px) {
  /* For tablets: */
  .col-s-1 {width: 8.33%;}
  .col-s-2 {width: 16.66%;}
  .col-s-3 {width: 25%;}
  .col-s-4 {width: 33.33%;}
  .col-s-5 {width: 41.66%;}
  .col-s-6 {width: 50%;}
  .col-s-7 {width: 58.33%;}
  .col-s-8 {width: 66.66%;}
  .col-s-9 {width: 75%;}
  .col-s-10 {width: 83.33%;}
  .col-s-11 {width: 91.66%;}
  .col-s-12 {width: 100%;}
}

@media only screen and (min-width: 768px) {
  /* For desktop: */
  .col-1 {width: 8.33%;}
  .col-2 {width: 16.66%;}
  .col-3 {width: 25%;}
  .col-4 {width: 33.33%;}
  .col-5 {width: 41.66%;}
  .col-6 {width: 50%;}
  .col-7 {width: 58.33%;}
  .col-8 {width: 66.66%;}
  .col-9 {width: 75%;}
  .col-10 {width: 83.33%;}
  .col-11 {width: 91.66%;}
  .col-12 {width: 100%;}
}
</style>
