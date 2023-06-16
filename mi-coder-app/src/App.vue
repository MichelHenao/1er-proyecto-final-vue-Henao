<template>
  <div id="app">
    <LoginComponent></LoginComponent>
    <NavbarComponent></NavbarComponent>
    <CardComponent></CardComponent>
    <FoterComponent></FoterComponent>
  </div>
</template>

<script>
import LoginComponent from './components/LoginComponent.vue';
import NavbarComponent from './components/NavbarComponent.vue';
import FoterComponent from './components/FoterComponent.vue';
import CardComponent from './components/CardComponent.vue';

export default {
  name: 'App',
  components: {
    LoginComponent,
    NavbarComponent,
    FoterComponent,
    CardComponent
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
