<template>
  <div class="alert alert-success" role="alert">
    <h4 class="alert-heading">{{titulo}}</h4>
    <label>
      <input type="text" v-bind:value="titulo" v-on:input="titulo = $event.target.value">
    </label>
    <hr>
    <p class="mb-0">Whenever you need to, be sure to use margin utilities to keep things nice and tidy.</p>
  </div>
</template>

<script>
  export default {
    name: 'Hello',
    data () {
      return {
        titulo: 'Usando VueJS!'
      }
    }
  }
</script>

</style>
