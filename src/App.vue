<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <center>
          <div class="form-group">
            <label for="email">Email address:</label>
            <input type="email" class="form-control" id="email">
          </div>
          <div class="form-group">
            <label for="pwd">Password:</label>
            <input type="password" class="form-control" id="pwd">
          </div>
          <div class="checkbox">
            <label><input type="checkbox"> Remember me</label>
          </div>
          <button type="submit" class="btn btn-default">Submit</button>
        </center>
      </div>
    </div>
  </div>
</template>

<script>
import {HTTP} from './http-common';

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created(){
    HTTP.get(`user`)
    .then(response => {
      console.log(response.data);
    })
    .catch(e => {
      console.log(e)
    })
  }
}
</script>

<style>
</style>
