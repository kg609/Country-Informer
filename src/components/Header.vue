<template>
  <div class="header">
<<<<<<< HEAD
    <!-- <h1>Country Informer</h1> -->
    <nav>
      <ul class="navbar">
        <a href="/" class="nav-link">
          <li class="fa fa-inbox nav-icon"></li>
        </a>
        <a href="/" class="nav-link">
          <li class="fa fa-group nav-icon"></li>
        </a>
        <a href="/" class="nav-link">
          <li class="fa fa-comments nav-icon"></li>
        </a>
      </ul>
    </nav>
    <hr/>>
=======
    <h1>Country Informer</h1>
    <nav>
      <ul class="navbar">
        <a href="/" class="nav-link">
          <li class="nav-item"> Home </li>
        </a>
        <a href="/" class="nav-link">
          <li class="nav-item"> About </li>
        </a>
        <a href="/" class="nav-link">
          <li class="nav-item"> Contact </li>
        </a>
      </ul>
    </nav>
>>>>>>> master
  </div>
</template>

<script>
  export default {
    name: 'Header',
    // components: {
    //   SearchBar
    // },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .header {
   color: white;
<<<<<<< HEAD
   /* padding-top: 20px; */
   /* background: #2c3e50; */
=======
   padding-top: 20px;
   background: #2c3e50;
>>>>>>> master
   text-align: center;
 }

 .navbar {
    display: flex;
<<<<<<< HEAD
    justify-content: flex-end;
    /* margin: 20px 0 0; */
    list-style: none;
    /* background: #ddd; */
=======
    justify-content: space-evenly;
    margin: 20px 0 0;
    list-style: none;
    background: #ddd;
>>>>>>> master
    height: auto;
    padding: 5px 0;
 }

 .navbar .nav-item {
<<<<<<< HEAD
    /* background: #2c3e50; */
    padding: 12px 25px;
    border-radius: 5px;
    border: 1px solid #000;
    color: #000;
    /* border: 1px solid #2c3e50; */
 }

 .nav-item:hover {
    background: #339FFF;
    border: 1px solid #339FFF;
    color: #FFF;
    /* border: 1px solid #2c3e50;
    color: #2c3e50; */
=======
    background: #2c3e50;
    padding: 12px 25px;
    border-radius: 5px;
    border: 1px solid;
 }

 .nav-item:hover {
    background: #ddd;
    border: 1px solid #2c3e50;
    color: #2c3e50;
>>>>>>> master
    transition: .3s ease-out all;
 }

 .nav-link {
    text-decoration: none;
    color: #FFF;
 }

 .nav-link:hover {
    text-decoration: none;
    color: #2c3e50;
 }

<<<<<<< HEAD
 .nav-icon {
   color: #777;
   padding: 10px;
 }

=======
>>>>>>> master
 
</style>
