<template>
<ul>
  <li><router-link class="active a" to="/">Home</router-link></li>
  <li><router-link to="/news" class="a">News</router-link></li>
  <li><router-link to="/contact" class="a">Contact</router-link></li>
  <li><router-link to="/about" class="a">About</router-link></li> 
</ul>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover:not(.active) {
  background-color: #111;
}

.active {
  background-color: #04AA6D;
}
</style>