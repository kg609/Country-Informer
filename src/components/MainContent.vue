<template>
  <div class="mainContent" >
      <div class="resultsContainer">
          <p>Some Data will be shown here</p>
          <br/>
          <!-- <p> info: {{this.info}}</p> -->
          <ul v-for="(country, index) in countries" class="countryList" v-bind:key="index">
              <div>
                  <li>
                    <strong>Country Name:</strong> {{ country.name }}, {{ country.region }}
                  </li>
              </div>
              <div>
                  <li v-for="(language, index) in country.languages" v-bind:key="index">
                    <strong>native language(s): </strong> {{ language.name }}
                  </li>
              </div>
              
          </ul>
          <br/>
          <br/>
          <p> {{this.countries.name}} </p>
          <br/>
          <br/>
          <br/>
      </div>
  </div>
</template>

<script>

    export default {
        name: 'MainContent',
        props:["countries"],
        data() {
            return {
                
            }
        },
        methods: {
            // showInfo() {
            //     console.log(`this is was the info that was passed: ${this.info}`)
            // }
        }
    }
</script>

<style scoped>
    .resultsContainer {
        display: grid;
        border: 1px solid #ddd;
        background: #2c3e50;
    }

    .countryList {
        margin: 10px auto;
        border: 1px solid #000;
        background: #ddd;
        color: #000;
        width: 50%;
        list-style: none;
        padding: 10px;
    }
</style>