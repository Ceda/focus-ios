<template>
  <div id="app">
    <div>
                  <SelectoInput
              />
                </div>

  </div>
</template>

<script>
import SelectoInput from './components/SelectoInput.vue'

export default {
  name: 'App',
  data: function() {
return {
    unit_type: '',
  };
},
  components: {
    SelectoInput
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
