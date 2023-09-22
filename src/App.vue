<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div>
                  <HelloWorld
                :options="['a', 'b', 'c', 'd', 'e', 'f']"
                v-model.lazy="unit_type"
                :show-custom="true"
                input-type="text"
                data-value-type="string"
              />
                </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data: function() {
return {
    unit_type: '',
  };
},
  components: {
    HelloWorld
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
