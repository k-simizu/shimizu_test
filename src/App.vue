<template>
  <div id="app">
    <SumUp></SumUp>
    <EditTable></EditTable>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import SumUp from './components/SumUp.vue'
import EditTable from './components/EditTable.vue'

export default {
  name: 'App',
  components: {
    SumUp,
    EditTable
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
