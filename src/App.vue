<script setup>
import { RouterLink, RouterView } from 'vue-router'

// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>
    <h1>Scanner App</h1>
  </header>
  <main>
    <RouterLink to="/"></RouterLink>
  </main>


  <RouterView />
</template>

<style>
template {
  background-color: rgb(255, 255, 255);
  padding-left: 1%;
  padding-right: 1%;
}

header {
  text-align: center;
}
</style>
