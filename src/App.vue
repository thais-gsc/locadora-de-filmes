<template>
  <div id="app">
    <h1>{{title}}</h1>
    <HelloWorld msg="hello!"/>

    <div class="horas">
      <p>{{parteDoDia()}}</p>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }, data(){
    return {
      title : "Locadora de Filmes",
      horas : new Date().getHours(),}
  }, methods:{
    parteDoDia(){
      if (this.horas < 12){
        return "Está de dia!"
      } else if (this.horas >= 12 && this.horas < 18){
        return "Está de tarde!"
      } else if (this.horas >= 18){
        return "Está de noite!"
      }
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
