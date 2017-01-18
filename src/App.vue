<template>
  <div id="app">
    <div class="container">
      <div v-for="u in userIDS">
        <user :id="u"></user>
      </div>
    </div>
  </div>
</template>
<script>
  import User from './components/User'

  export default {
    name: 'app',
    data: function () {
      return {
        userIDS: [1, 2, 3, 4, 5,6,7,8,9,10]
      }
    },
    components: {
      User
    }
  }

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

  .container{
    align-items: center;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
  }

</style>
