<template>
  <div id="app">
    <Header />
    <SearchBar v-on:submitted-info="getInfo" />
    <MainContent :countries=results />
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
    MainContent
  },
  props: {
    
  },
  data() {
    return {
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
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  /* color: #2c3e50; */
  
}

</style>
