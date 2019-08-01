<template>
  <div class="searchBar" >
      <p class="introText">Enter in a country that you are interested to learn more about. </p>
      <form v-on:submit.prevent="onSubmit(term)" >
        <input type="text" placeholder="Search..." v-model="term">
        <input type="submit" value="Submit"  class="btn" />
      </form>
      <strong>The search term is: {{ term }}</strong><br/><br/>
  </div>
</template>

<script>

    export default {
        name: 'SearchBar',
        data() {
            return {
                term: ''
            }
        },
        methods: {
           onSubmit(term){
               console.log(`the search term was: ${term}`)

               // Sends event listener and search term to parent component
               this.$emit('submitted-info', term)
               this.term = ''
           }
        }
    }
</script>

<style scoped>
    
.introText{
    margin: 20px auto; 
    text-align: center;
}

form {
    display: flex;
    margin: 20px auto;
    width: 100%;
    max-width: 900px; 
}

input[type="text"] {
    width:100%;
    padding: 10px 20px;
    border: 1px solid #000;
    font-weight: 800;
    
}

input[type="submit"] {
    padding: 10px 50px;
    color: #FFF;
    background: #2c3e50;
    border: 1px solid #2c3e50;
    /* font-size:  */
    font-weight: 800;
    letter-spacing: 1px;
}

input[type="submit"]:hover {
    color: #2c3e50;
    background: lightgrey;
    /* opacity: .6; */
    transition: all .5s ease-in-out;
    cursor: pointer;
}

</style>