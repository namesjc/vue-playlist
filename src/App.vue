<template>
  <div id="app">
    <app-header @titleChanged="updateTitle($event)" :title="title"></app-header>
    <users :users="usersAarry"></users>
    <users :users="usersAarry"></users>
    <app-footer :title="title"></app-footer>
  </div>
</template>

<script>

import Users from './components/Users'
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  name: 'App',
  data() {
    return {
      usersAarry: [
        {name: "Echo", position: "Manager", show: false},
        {name: "Marco", position: "Web developer", show: false},
        {name: "Steve", position: "Captain America", show: false},
        {name: "Tony", position: "Icon Man", show: false},
        {name: "Peter", position: "Sipder Man", show: false},
        {name: "Bruce", position: "Hulk", show: false}
      ],
  title: "Passing a value(number string boolean)"         
    }   
  },
  methods: {
    updateTitle(changedTitle) {
      this.title = changedTitle;
    }
  },
  components: {
    "users": Users,
    "app-header": Header,
    "app-footer": Footer
  }
}
</script>

<style scoped>
  h1 {
    color: purple;
  }
</style>
