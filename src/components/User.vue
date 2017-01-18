<template>
  <div class="container">
    <img src="http://librarianinblack.net/librarianinblack/wp-content/uploads/2014/10/Spy.png" alt="">
    <div class="user">
      <h1>{{name}}</h1>
      <p>{{email}}</p>
    </div>
</template>
<script>
  import axios from 'axios'
  export default {
    props: ['id'],
    data: function () {
      return {
        name: '',
        email: ''
      }
    },
    beforeMount() {
      axios.get('https://jsonplaceholder.typicode.com/users/' + this.id)
        .then((response) => {
          this.name = response.data.name
          this.email = response.data.email
        })
    }
  }

</script>
<style scoped>
  h1,
  h2 {
    font-weight: normal;
  }
  
  p {
    margin-top: 0px;
  }
  
  .container{
    outline: solid;
    padding: 25px;
    margin: 5px;
    width: 350px;
    display: flex;
    flex-direction: column;
  }
  img{
    width: 150px;
  }

</style>
