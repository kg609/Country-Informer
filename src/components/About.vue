<template>
  <div class="about">
      <div class="about-content">
        <!-- Country specific information based on card chosen -->
        <div class="imageContainer">
            <div class="backgroundImg1">

            </div>
        </div>

        <h1>About</h1>

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
            Euismod nisi porta lorem mollis aliquam ut porttitor. 
            Purus in mollis nunc sed id semper risus in hendrerit. Donec massa sapien faucibus et. 
            Lacus laoreet non curabitur gravida arcu. Faucibus scelerisque eleifend donec pretium vulputate sapien nec. Nunc id cursus metus aliquam eleifend mi in nulla posuere. 
            Malesuada proin libero nunc consequat interdum varius sit amet mattis. Aenean vel elit scelerisque mauris pellentesque pulvinar. Aliquet eget sit amet tellus cras adipiscing. 
            At risus viverra adipiscing at. Lacus luctus accumsan tortor posuere ac ut consequat. Ultrices in iaculis nunc sed augue. Scelerisque viverra mauris in aliquam sem fringilla ut. 
            Pretium vulputate sapien nec sagittis aliquam malesuada bibendum arcu. Neque laoreet suspendisse interdum consectetur libero. Nisi lacus sed viverra tellus in hac habitasse. 
            Pretium nibh ipsum consequat nisl. Nisl nisi scelerisque eu ultrices. Facilisi etiam dignissim diam quis enim lobortis scelerisque fermentum dui.
        </p><br/>
      </div>

      <div class="">
        <div class="imageContainer">
            <div class="backgroundImg2">

            </div>
        </div>

        <h1>Popular Tourist Areas</h1>

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
            Euismod nisi porta lorem mollis aliquam ut porttitor. 
            Purus in mollis nunc sed id semper risus in hendrerit. Donec massa sapien faucibus et. 
            Lacus laoreet non curabitur gravida arcu. Faucibus scelerisque eleifend donec pretium vulputate sapien nec. Nunc id cursus metus aliquam eleifend mi in nulla posuere. 
            Malesuada proin libero nunc consequat interdum varius sit amet mattis. Aenean vel elit scelerisque mauris pellentesque pulvinar. Aliquet eget sit amet tellus cras adipiscing. 
            At risus viverra adipiscing at. Lacus luctus accumsan tortor posuere ac ut consequat. Ultrices in iaculis nunc sed augue. Scelerisque viverra mauris in aliquam sem fringilla ut. 
            Pretium vulputate sapien nec sagittis aliquam malesuada bibendum arcu. Neque laoreet suspendisse interdum consectetur libero. Nisi lacus sed viverra tellus in hac habitasse. 
            Pretium nibh ipsum consequat nisl. Nisl nisi scelerisque eu ultrices. Facilisi etiam dignissim diam quis enim lobortis scelerisque fermentum dui.
        </p><br/>
      </div>
  </div>
</template>

<script>
  export default {
    name: 'About',
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 
.imageContainer {
    /* border: 1px solid; */
    height: 50vh;
    margin: 20px auto;
  }

.backgroundImg1 {
    height: 100%;
    background: url(https://images.unsplash.com/photo-1526778548025-fa2f459cd5c1?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=100%&q=60) no-repeat center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: 100%;
}

.backgroundImg2 {
    height: 100%;
    background: url(https://images.pexels.com/photos/2087391/pexels-photo-2087391.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=100%) no-repeat center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: 100%;
}

</style>
