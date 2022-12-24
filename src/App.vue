<template>
  <div id="app">
    <WelcomeTitle/>
    <IrohQuotes/>
  </div>
</template>

<script>
import WelcomeTitle from './components/WelcomeTitle.vue'
import IrohQuotes from './components/IrohQuotes.vue'

export default {
  name: 'App',
  components: {
    WelcomeTitle,
    IrohQuotes,
  }
}
</script>

<style>
#app {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}
</style>
