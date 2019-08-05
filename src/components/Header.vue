<template>
  <div class="header">
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
  </div>
</template>

<script>
  export default {
    name: 'Header',
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .header {
   color: white;
   padding-top: 20px;
   background: #2c3e50;
   text-align: center;
 }

 .navbar {
    display: flex;
    justify-content: space-evenly;
    margin: 20px 0 0;
    list-style: none;
    background: #ddd;
    height: auto;
    padding: 5px 0;
 }

 .navbar .nav-item {
    background: #2c3e50;
    padding: 12px 25px;
    border-radius: 5px;
    border: 1px solid;
 }

 .nav-item:hover {
    background: #ddd;
    border: 1px solid #2c3e50;
    color: #2c3e50;
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

 
</style>
