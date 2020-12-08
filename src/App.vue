<!--
  Name: Chase Cook
  Assignment: Popular TV Shows
  Class: Web Dev II Markley
-->

<template>

<div class="container" id="mainDiv">
  <div id="app">
    <Header/>
    <Card/>
  </div>
</div>

</template>

<script>
import Header from './components/Header.vue'
import Card from './components/Card.vue'

export default {
  name: 'App',
  // Header and Card components for adding to the mainDiv container
  components: {
    Header,
    Card
  }
}
</script>

<style>
html > body
{
  background-color: #2A2A2E;
}

#app
{
  background: #38383D;
  padding-bottom: 15px;
}

#mainDiv
{
  background: #38383D;
  margin-top: 50px;
  margin-bottom: 50px;
  border-radius: 10px;
}
</style>

