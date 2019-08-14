<template>
  <div class="mainContent" >
      <div class="resultsContainer">
          <!-- <p>Some Data will be shown here</p> -->
          <ul v-for="(country, index) in countries" class="countryListCard" v-bind:key="index" >
              <div class="countryName">
                  <li>
                    <strong>Country Name:</strong> {{ country.name }}, {{ country.region }}
                  </li>
              </div>
              <div class="countryLanguage">
                  <li v-for="(language, index) in country.languages" v-bind:key="index">
                    <strong>native language(s): </strong> {{ language.name }}
                  </li>
              </div>

              
                  <div class="btnContainer">
                      <button class="btn-learn" v-on:click="showInfo(country)">Learn More</button>
                  </div>
              <!-- <div class="countrySpecifics">
                  <li v-if="">
                    <strong>native language(s): </strong> {{ language.name }}
                  </li>
              </div>   -->
          </ul>
          <br/>
          <br/>
          <!-- <p> {{this.countries.name}} </p> -->
      </div>
  </div>
</template>

<script>

    export default {
        name: 'MainContent',
        props:["countries"],
        data() {
            return {
                isOpen: false
            }
        },
        methods: {
            showInfo(el) {
                console.log(el)
                console.log(`this is was the info that was passed: ${el}`)
                this.isOpen =  true
                // this.$emit('learn-more-click', el)
            }
        }
    }
</script>

<style scoped>
    .resultsContainer {
        display: grid;
        grid-template-columns: auto auto auto;
        grid-template-rows: auto auto auto;
        border: 1px solid #ddd;
        background: #2c3e50;
    }

    .countryListCard {
        margin: 10px auto;
        border: 1px solid #000;
        background: #ddd;
        color: #000;
        width: 50%;
        list-style: none;
        padding: 10px;
    }

    .btnContainer {
        display: flex;
    }

    .btn-learn {
        padding: 10px;
        margin: 10px auto;
        background: #2c3e50;
        padding: 12px 25px;
        border-radius: 5px;
        border: 1px solid #2c3e50;
        color: #FFF;

    }

    .btn-learn:hover {
        background: #ddd;
        color: #2c3e50;
        transition: .3s ease-in-out all;
    }
</style>