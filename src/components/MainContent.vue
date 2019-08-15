<template>
  <div class="mainContent" >
      <div class="resultsContainer col-" v-if="isVisible" >
          <!-- {{ console.log(`The results is open value: ${isOpen`) }} -->
          <!-- <p>Some Data will be shown here</p> -->
          
            <ul v-for="(country, index) in countries" class="countryListCard col-s-4 col-" v-bind:key="index" >
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
                        <button class="btn-learn-more" v-on:click="showInfo(country,index)">Learn More</button>
                    </div>
                </div>
            </ul> 
      </div>

      <!-- Country specific information based on card chosen -->
            <div class="imageContainer" v-if="isHidden">
                <div class="backgroundImg">

                </div>
            </div>

            <div>
                <h1> {{ countryObject.name }} </h1>
            </div>
              <div class="countrySpecificsContainer col-" v-if="isHidden">
                  
                  <ul class="specificListInfo">
                    <div class="specificCardInfo">
                        <h2>General Info</h2>
                        <hr />

                        <div class="general-info">
                            <li>
                                <strong>Native Name: </strong> {{ countryObject.nativeName}}
                            </li>
                            <li>
                                <strong>Country Population: </strong> {{ countryObject.population }}
                            </li>
                            <li>
                                <strong>Country Capital: </strong> {{ countryObject.capital }}
                            </li>
                            <li>
                                <strong>Country Flag: </strong> {{ countryObject.flag }}
                            </li>
                        </div>
                    </div>

                    <div class="specificCardInfo">
                        <h2>Trade Info</h2>
                        <hr />

                        <div class="trade-info">
                            <li v-for="(language, index) in countryObject.languages"  v-bind:key="index">
                                <strong> Native Language(s) Name: </strong> {{ language.nativeName }}
                            </li>
                            <li v-for="(currency, index) in countryObject.currencies"  v-bind:key="index">
                                <strong>Country Currencies Name: </strong> {{ currency.name }} <br/>
                                <strong>Country Currencies Abbreviation: </strong> {{ currency.code }} <br/>
                                <strong>Country Currencies Symbol: </strong> {{ currency.symbol }} 
                            </li>
                        </div> 
                    </div>

                    <div class="specificCardInfo">
                        <h2>Geographic Info</h2>
                        <hr />

                        <div class="geographic-info">
                            <li v-for="(coord, index) in countryObject.latlng"  v-bind:key="index">
                                <strong>Country Lat/Long Location: </strong> {{ coord }}
                            </li>
                            <li>
                                <strong>Country Region: </strong> {{ countryObject.region }}
                            </li>
                            <li>
                                <strong>Country Sub Region(s): </strong> {{ countryObject.subregion }}
                            </li>
                            <li v-for="(timezone, index) in countryObject.timezones"  v-bind:key="index">
                                <strong>Country timezone(s): </strong> {{ timezone }}
                            </li>
                        </div>
                    </div>
                  </ul>

                  <div class="btnbackContainer">
                      <button class="btn-go-back" v-on:click="showInfo">Go Back</button>
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
        grid-gap: 20px;
        /* border: 1px solid #ddd;
        background: #2c3e50; */
    }

    h1 {
        text-align: center;
    }
    /* .countryListContainer {
        display: grid;
        grid-template-columns: auto auto auto;
        grid-template-rows: auto auto auto;
        border: 1px solid #ddd;
        background: #2c3e50;
    } */

    .countryListCard {
        margin: auto;
        /* border: 1px solid #000; */
        background: #ddd;
        color: #000;
        width: 500px;
        /* height: 150px; */
        line-height: 1.3rem;
        list-style: none;
        padding: 10px;
        box-shadow: 0px 0px 5px 0px rgba(0,0,0,0.75);
        border-radius: 5px;
    }

    .countrySpecificsContainer {
        /* border: 1px solid #000; */
        /* background: #ddd; */
        color: #000;
        /* padding: 30px; */
        max-width: 1200px;
        margin: 50px auto;
    }

    .imageContainer {
        border: 1px solid;
        height: 50vh;
        margin: 20px auto;
    }

    .backgroundImg {
        height: 100%;
        background: url(https://upload.wikimedia.org/wikipedia/commons/5/53/Maroon_Bells_%2811553%29a.jpg) no-repeat center;
        -webkit-background-size: cover;
        -moz-background-size: cover;
        -o-background-size: cover;
        background-size: cover;
    }

    .specificListInfo {
        list-style: none;
        display: grid;
        grid-template-columns: auto auto auto;
        grid-template-rows: auto auto auto;
        grid-column-gap: 20px;
        grid-row-gap: 0;
    }

    .specificCardInfo {
        /* border: 1px solid #000; */
        /* margin: 0 auto; */
        padding: 10px 20px;
        line-height: 1.5rem;
        box-shadow: 0px 0px 5px 0px rgba(0,0,0,0.75);
        background: #EEE;
        border-radius: 5px;
    }

    .general-info, .trade-info, .geographic-info {
        margin-top: 10px;
    }

    .btnContainer {
        display: flex;
    }

    .btn-learn-more {
        padding: 10px;
        margin: 10px auto;
        background: #2c3e50;
        padding: 12px 25px;
        border-radius: 5px;
        border: 1px solid #2c3e50;
        color: #FFF;

    }

    .btn-learn-more:hover {
        background: #ddd;
        color: #2c3e50;
        transition: .3s ease-in-out all;
    }

    .btn-go-back {
        padding: 10px;
        margin-top: 50px;
        background: #2c3e50;
        padding: 12px 25px;
        border-radius: 5px;
        border: 1px solid #2c3e50;
        color: #FFF;

    }

    .btn-go-back:hover {
        background: #ddd;
        color: #2c3e50;
        transition: .3s ease-in-out all;
    }


    /* Media Queries */
/* For mobile phones: */
/* @media only screen and (max-width: 600px) {
    .countryListCard {
        display: block;
    }
}  */

[class*="col-"] {
  width: 100%;
  display: block;
  margin: 20px auto;
  padding: 20px;
}

@media only screen and (min-width: 600px) {
  /* For tablets: */

  .resultsContainer, .countrySpecificsContainer {
      display: grid;
      grid-template-columns: auto auto auto;
      grid-template-rows: auto auto auto;
      grid-gap: 20px;
  }
  

}

@media only screen and (min-width: 768px) {
  /* For desktop: */

}

    
</style>