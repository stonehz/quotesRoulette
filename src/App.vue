<template>
  <div id="app">
    <header>
      <Header />
    </header>
    <main>
      <MainPage msg="Welcome to Your Vue.js App"/>
    </main>
    <footer>
      <Footer />
    </footer>

  </div>
</template>

<script>

import MainPage from './components/layout/MainPage.vue';
import Header from './components/layout/Header.vue';
import Footer from './components/layout/Footer.vue';

export default {
  name: 'app',
  components: {
    Header,
    MainPage,
    Footer,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
