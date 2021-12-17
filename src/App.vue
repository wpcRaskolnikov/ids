<template>
  <div id="app">
    <v-app>
      <NavigationBar/>
    </v-app>
    <Network/>
  </div>
</template>

<script>
import Network from './components/Network'
import NavigationBar from "./components/NavigationBar"

export default {
  name: 'App',
  components: {
    NavigationBar,
    Network
  }
}
</script>

<style>

</style>
