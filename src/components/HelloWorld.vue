<template>
  <div class="ui container">
    <div class="ui two column centered grid">
      <div class="column">
        <button class="ui primary basic button" type="button" @click="showAlert">Alerter</button>
        <alert  cls='error' :msgContent="msgContent" :msgHeader="msgHeader" v-if="alert" @close="hideAlert"></alert>
      </div>
      <div class="column">
        <todo></todo>
      </div>
    </div>
    <div class="ui two column centered grid">
      <carousel>
    <carousel-slide>
      <img src = "http://lorempicsum.com/up/800/400/4" alt = "1">
    </carousel-slide>
    <carousel-slide>
      <img src = "http://lorempicsum.com/up/800/400/9" alt = "1">
    </carousel-slide>
  </carousel>

    </div>
  </div>
</template>

<script>
import alert from './alert'
import todo from './toDo'
import Carousel from './carousel/Carousel'
import CarouselSlide from './carousel/CarouselSlide'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msgContent: 'Welcome to Your Vue.js App',
      msgHeader: 'Titre',
      alert: false
    }
  },
  components: {
    alert,
    todo,
    Carousel,
    CarouselSlide
  },
  methods: {
    showAlert () {
      this.alert = true
    },
    hideAlert () {
      this.alert = false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
