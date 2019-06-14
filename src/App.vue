<template>
  <div class="jumbotron jumbotron-fluid">
    <div class="container">
      <button class="btn btn-success btn-lg btn-block" @click="aumentar">Aumentar</button>
      <button class="btn btn-danger btn-lg btn-block" @click="aumentar2">Aumentar 2</button>
      <button class="btn btn-warning btn-lg btn-block" @click="diminuir">Diminuir</button>
      <hr>
      <button class="btn" :class="[classCSS, {girar: aplicarGirar}]" @click="aplicarC1 = !aplicarC1">CLASS</button>
      <input type="text" v-model="classCSS">
      <hr>
      <div class="alert alert-warning" role="alert">Contador: <strong>{{ contador }} | {{ contador2 }}</strong></div>
      <div class="alert alert-success" role="alert">Resultado: <strong>{{ resultado }}</strong></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      contador: 0,
      contador2: 0,
      aplicarC1: false,
      classCSS: 'btn-primary btn-lg btn-block',
      aplicarGirar: false
    }
  },
  computed: {
    resultado  () {
      console.log('metodo computed resultado chamado...')
      return this.contador >= 5 ? 'Maior ou igual a 5' : 'Menor que 5'
    },
    estilo1() {
      return {
        'btn-primary btn-lg btn-block': this.aplicarC1,
        'btn-warning btn-lg btn-block': !this.aplicarC1
      }
    }
  },
  methods: {
    aumentar() {
      this.contador++
    },
    aumentar2() {
      this.contador2++
    },
    diminuir() {
      this.contador--
    }
  },
  watch: {
    contador (novo, antigo) {
      console.log(novo, antigo)
      setTimeout(() => {
        this.contador = 0
      }, 2000)
    }
  }
}
</script>

<style>
  .c1 {
    width: 100%;
  }
  .girar {
    transform: rotate(45deg);
  }
</style>
