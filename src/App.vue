<template>
  <div id="app">
    <LeaseList/>
  </div>
</template>

<script>
import LeaseList from "./components/LeaseList";

export default {
  name: 'App',
  components: {
    LeaseList,
  }
}
</script>

<style>
body {
  background-color: #42b983;
}
</style>
