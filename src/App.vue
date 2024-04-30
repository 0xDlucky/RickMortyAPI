<script setup>
import {ref} from "vue"

let num = ref(0)
</script>

<template>
  <div>
    <img class="logo" src="https://res.cloudinary.com/dkfzj9tmk/image/upload/v1677166689/backend-project/Rick-And-Morty-Logo-Transparent-File_arpmel.png" alt="">
  </div>
  <nav class="navbar navbar-expand-lg navbar-dark border-bottom border-body">
    <div class="container-fluid">
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbar" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/" style="color: #42b983;"><strong>Home</strong></router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/about" style="color: #42b983;"><strong>About</strong></router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="main">
      <router-view></router-view>
  </div>
</template>

<style>
*{
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

