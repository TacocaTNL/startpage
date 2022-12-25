<template>
  <div id="app">
    <div class="grid-container">
      <div class="blurry-container">
        <WelcomeTitle class="title"/>
        <IrohQuotes class="quote"/>
      </div>
      <div class="app-container">
        <AppCard 
          v-for="app in appCards"
          :key="app.id"
          :app="app"
        />
      </div>
    </div>
  </div>
</template>

<script>
import WelcomeTitle from './components/WelcomeTitle.vue'
import IrohQuotes from './components/IrohQuotes.vue'
import AppCard from './components/AppCard.vue'

export default {
  name: 'App',
  components: {
    WelcomeTitle,
    IrohQuotes,
    AppCard,
  },
  data() {
    return {
      appCards: [
        {id: 0, name: "youtube", url: "https://www.youtube.com/feed/subscriptions/"},
        {id: 1, name: "netflix", url: "https://www.netflix.com/browse/"},
        {id: 2, name: "twitch", url: "https://www.twitch.tv/directory/following/"},
        {id: 3, name: "whatsapp", url: "https://web.whatsapp.com/"},
        {id: 4, name: "tue", url: "https://canvas.tue.nl/"},
        {id: 5, name: "github", url: "https://www.github.com/"},
      ]
    }
  }
}
</script>

<style>
@font-face {
  font-family: 'Roboto';
  src: url('./fonts/Roboto-Regular.ttf');
  font-weight: 400;
}

@font-face {
  font-family: 'Roboto';
  src: url('./fonts/Roboto-Bold.ttf');
  font-weight: 700;
}

body {
  font-family: 'Roboto', sans-serif;
  margin: 0;
  border: 0;
  background: url('./assets/forest.jpg') center no-repeat fixed;
}

.grid-container {
  display: grid;
  height: 100vh;
  width: 100vw;
  justify-items: stretch;
  grid-template-columns: 30% auto auto;
  grid-template-rows: auto;
  color: white;
}

.blurry-container {
  display: grid;
  height: 100%;
  width: 100%;
  grid-template-columns: auto;
  grid-template-rows: 1fr auto 1fr;
  backdrop-filter: blur(14px);
}

.title {
  grid-area: 2 / 1 / 3 / 2;
}

.quote {
  align-self: center;
  text-align: center;
  grid-area: 3 / 1 / 4 / 2;
}

.app-container {
  display: flex;
  flex-flow: column nowrap;
  height: 100%;
  justify-content: space-evenly;
}

</style>
