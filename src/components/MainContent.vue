<template>
  <div class="mainContent" >
      <div class="resultsContainer" v-if="isVisible" >
          <!-- {{ console.log(`The results is open value: ${isOpen`) }} -->
          <!-- <p>Some Data will be shown here</p> -->
          
            <ul v-for="(country, index) in countries" class="countryListCard" v-bind:key="index" >
                <div class="countryListContainer" >
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
                        <button class="btn-learn" v-on:click="showInfo(country,index)">Learn More</button>
                    </div>
                </div>
            </ul> 
      </div>

      <!-- Country specific information based on card chosen -->
              <div class="countrySpecifics" v-if="isHidden">
                  <h1> {{ countryObject.name }} </h1>
                  <ul> 
                    <li>
                        <strong>Country Population: </strong> {{ countryObject.population }}
                    </li>
                  </ul>

                  <div class="btnContainer">
                        <button class="btn-learn" v-on:click="showInfo">Go Back</button>
                    </div>
              </div> 
  </div>
</template>

<script>

    export default {
        name: 'MainContent',
        props:["countries"],
        data() {
            return {
                isVisible: true,
                isHidden: false,
                countryObject: {},
                indexOfCountryObj: 0
            }
        },
        methods: {
            showInfo(el, index) {
                // console.log(el)
                // console.log(`this is was the info and index that was passed: ${index}`)

                this.isVisible = !this.isVisible
                this.isHidden = !this.isHidden
                // console.log(`is Visible: ${this.isVisible}`)
                // console.log(`is Hidden: ${this.isHidden}`)

                this.countryObject= el
                this.indexOfCountryObj = index

                // console.log('This is the country object:' + this.countryObject)
                // console.log('country index is:' + this.indexOfCountryObj)
                return (this.countryObject, this.indexOfCountryObj)
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

    /* .countryListContainer {
        display: grid;
        grid-template-columns: auto auto auto;
        grid-template-rows: auto auto auto;
        border: 1px solid #ddd;
        background: #2c3e50;
    } */

    .countrySpecifics {
        border: 1px solid #000;
        background: #ddd;
        color: #000;
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