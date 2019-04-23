<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button v-on:click="randomQuote()"> Touch me if you want to get inspired! </button>
    <hr>
    <h2> {{ quotes[rand] }} </h2>
    <hr>
  </div>
</template>

<script>
const randomize = () => Math.floor(Math.random() * 10);

export default {
  name: 'MainPage',
  data() {
    return {
      quotes: ['1', '2', '3', '4', '5', '6', '7', '8', '9'],
      rand: -1,
    };
  },
  props: {
    msg: String,
  },
  methods: {
    randomQuote() {
      console.log('test');
      this.rand = randomize();
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
