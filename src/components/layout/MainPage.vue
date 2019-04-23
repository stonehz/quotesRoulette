<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button v-on:click="randomQuote()"> Touch me if you want to get inspired! </button>
    <hr>
    <h2 v-if="rand >= 0"> {{ list[rand].quote }} </h2>
    <h4 v-if="rand >= 0" > by {{ list[rand].author }} </h4>
    <hr>
  </div>
</template>

<script>
import { quoteList as quotes } from '../../data/quotes';

const randomize = size => Math.floor(Math.random() * size);

export default {
  name: 'MainPage',
  data() {
    return {
      list: quotes,
      rand: -1,
    };
  },
  props: {
    msg: String,
  },
  methods: {
    randomQuote() {
      this.rand = randomize(quotes.length);
      console.log(this.rand);
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
