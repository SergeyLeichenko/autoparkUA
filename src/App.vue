<template>
  <v-app class="app">
    <Header />
    <Nav />

    <v-main>
      <Main />
    </v-main>
  </v-app>
</template>

<script>
import Header from './components/vHeader'
import Nav from './components/vNavBar'
import Main from './components/vMain.vue'

export default {
  name: 'App',

  components: {
    Header,
    Nav,
    Main
  },

  data: () => ({
    //
  }),
};
</script>

<style scoped lang="scss">
.app {
  max-width: 1180px;
  margin: auto;
  padding-top: 10px;
}
</style>
