<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="actionable">
      <button v-if="!loading" v-on:click="randomQuote()">
        Touch me if you want to get inspired!
      </button>
      <div v-else class="lds-hourglass"></div>
    </div>
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
      loading: false,
    };
  },
  props: {
    msg: String,
  },
  methods: {
    randomQuote() {
      this.loading = true;
      setTimeout(() => {
        this.rand = randomize(quotes.length);
        console.log(this.rand);
        this.loading = false;
      }, 1000);
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
.lds-hourglass {
  display: inline-block;
  position: relative;
  width: 64px;
  height: 64px;
}
.lds-hourglass:after {
  content: " ";
  display: block;
  border-radius: 50%;
  width: 0;
  height: 0;
  margin: 6px;
  box-sizing: border-box;
  border: 26px solid #000;
  border-color: #000 transparent #000 transparent;
  animation: lds-hourglass 1.2s infinite;
}
@keyframes lds-hourglass {
  0% {
    transform: rotate(0);
    animation-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
  50% {
    transform: rotate(900deg);
    animation-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
  }
  100% {
    transform: rotate(1800deg);
  }
}
.actionable {
  height: 70px;
  display: flex;
  justify-content: center;
}
button {
  background-color:#44c767;
  outline: 0;
  -moz-border-radius:28px;
  -webkit-border-radius:28px;
  border-radius:28px;
  border:1px solid #18ab29;
  display:inline-block;
  cursor:pointer;
  color:#ffffff;
  font-family:Arial;
  font-size:17px;
  padding:16px 31px;
  text-decoration:none;
  text-shadow:0px 1px 0px #2f6627;
}
button:hover {
  background-color:#5cbf2a;
}
</style>
