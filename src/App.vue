<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- //<HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div id="appRoot">
    <HeaderComponent></HeaderComponent>
    <hr>
    <ListComponent></ListComponent>
    <hr>
    <FooterComponent></FooterComponent>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import HeaderComponent from './components/HeaderComponent.vue'
import ListComponent from './components/ListComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    ListComponent,
    FooterComponent

  }
}
</script>

<style>
#appRoot{
  /* background-color: gray; */
  background-color: lightcyan;
}
</style>
