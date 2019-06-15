<template>
  <div class="jumbotron jumbotron-fluid">
    <div class="list-group">
      <a href="#" class="list-group-item list-group-item-action" v-for="post in posts">
        <div class="list-group">
          <a href="#" class="list-group-item list-group-item-action" v-for="(data, key, index) in post" :key="index">{{data}} - {{key}} - ({{index}})</a>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'app',
  data () {
    return {
      posts: [],
      errors: []
    }
  },
  created() {
    axios.get(`https://servicodados.ibge.gov.br/api/v1/localidades/estados`)
      .then(response => {
        this.posts = response.data
      })
      .catch(e => {
        this.errors.push(e)
      })
  }
}
</script>

<style>
</style>
