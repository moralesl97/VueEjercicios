<template>
  <div id="app">
     Nombre del equipo a consultar: <input type="text" v-model="equipo">
    <InfoEquipo :team="this.equipo" />
  </div>
</template>

<script>
import InfoEquipo from './components/infoEquipo.vue'

export default {
  name: 'App',
  components: {
    InfoEquipo
  },
  data(){
    return{
      equipo: '',
    }
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
