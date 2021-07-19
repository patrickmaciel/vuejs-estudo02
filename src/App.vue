<template>
  <div id="app">
    {{ name }} - {{ email }}
    <button @click="login('patrickmaciel.info@gmail.com')">Logar</button>
    <br>
    <span style="color: green;" v-if="isValidEmail">Este e-mail não é válido</span>
    <span v-else-if="type === 1">Igual 1</span>
    <span v-else-if="type === 2">Igual 2</span>
    <span v-else-if="type === 3">Igual 3</span>
    <span style="color: red;" v-else>Este e-mail não é válido</span>
    <!--    <p @mouseover="hover">Mouse hover</p>-->
    <hr>
    <a href="#">Ir para o Login</a>

    <login />
  </div>
</template>

<script>
import Login from './components/Login/login'

export default {
  name: 'App',
  components: {
    Login,
  },
  data () {
    return {
      name: 'Patrick Maciel',
      email: '',
      type: 3
    }
  },
  computed: {
    getName () {
      return this.name
    },
    isValidEmail () {
      return this.email.includes('patrickmaciel.info@gmail.com')
    }
  },
  methods: { // objeto de métodos
    login (params) {
      this.email = params
    },
    hover () {
      alert('hover')
    }
  }
}
</script>

<style>
</style>
