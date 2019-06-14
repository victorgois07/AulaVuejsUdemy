<template>
  <div class="container">
    <form class="form-signin">
      <div class="text-center mb-4">
        <img class="mb-4" src="https://getbootstrap.com/docs/4.3/assets/brand/bootstrap-solid.svg" alt="" width="72" height="72">
        <h1 class="h3 mb-3 font-weight-normal">Floating labels</h1>
        <template v-if="logado">
          <p>Build form controls with floating labels via the <code>:placeholder-shown</code> pseudo-element. <a href="https://caniuse.com/#feat=css-placeholder-shown">Works in latest Chrome, Safari, and Firefox.</a></p>
        </template>
        <p v-if="logado">Usuário Logado: {{ nome }}</p>
        <p v-else-if="anonimo">Navegando como Animo</p>
        <p v-else>Nenhum usuário logado</p>
        <button class="btn btn-danger" type="button" @click="logado = !logado">{{ logado ? 'Sair' : 'Entrar' }}</button>
        <hr>
        <input type="checkbox" v-model="anonimo">
        <footer v-show="logado">
          Desenvolvido pra vc!!
        </footer>
        <footer v-show="!logado">
          Desenvolvido pra vc anonimo!!
        </footer>
      </div>

      <div class="form-label-group">
        <input type="email" id="inputEmail" class="form-control" placeholder="Email address" required autofocus>
        <label for="inputEmail">Email address</label>
      </div>

      <div class="form-label-group">
        <input type="password" id="inputPassword" class="form-control" placeholder="Password" required>
        <label for="inputPassword">Password</label>
      </div>

      <div class="checkbox mb-3">
        <label>
          <input type="checkbox" value="remember-me"> Remember me
        </label>
      </div>
      <button class="btn btn-lg btn-primary btn-block" type="submit">Sign in</button>
      <p class="mt-5 mb-3 text-muted text-center">&copy; 2017-2019</p>
    </form>

  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      nome: 'Maria',
      logado: false,
      anonimo: false
    }
  }
}
</script>

<style>
  .bd-placeholder-img {
    font-size: 1.125rem;
    text-anchor: middle;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

  @media (min-width: 768px) {
    .bd-placeholder-img-lg {
      font-size: 3.5rem;
    }
  }
</style>
