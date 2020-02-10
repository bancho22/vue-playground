<template>
  <div id="app" :class="{darkMode: isDarkModeEnabled}">
    <SwitchButton
      v-model="isDarkModeEnabled"
      :color="isDarkModeEnabled ? 'var(--lightColor)' : undefined"
    >
      Dark mode: {{ darkModeState }}
    </SwitchButton>
    <img alt="Vue logo" src="../assets/logo.png">
    <h1>Welcome to Bancho`s First Vue.js TODO (BOOORING) App with (not so boring) Dark Mode</h1>
    <HelloToDo />
  </div>
</template>

<script>
import HelloToDo from './HelloToDo/HelloToDo.vue'
import SwitchButton from '../components/SwitchButton.vue'

export default {
  name: 'App',
  components: {
    HelloToDo,
    SwitchButton
  },
  data: function () {
    return {
      isDarkModeEnabled: false
    }
  },
  computed: {
    darkModeState: function () {
      return this.isDarkModeEnabled ? 'ON' : 'OFF'
    }
  }
}
</script>

<style>
html {
  height: 100vh;
  overflow: hidden;
}
body {
  height: 100%;
  margin: 0;
}

#app {
  --lightColor: #e4e8ec;
  --darkColor: #4e4e4e;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding-top: 60px;
  height: 100%;
  background-color: var(--lightColor);
}

#app.darkMode {
  background-color: var(--darkColor);
  color: var(--lightColor);
}

#app.darkMode .switch-button {
  background-color: transparent;
}

.switch-button-control {
  position: absolute;
  right: 3%;
  top: 5%;
  font-weight: bold;
}
</style>
