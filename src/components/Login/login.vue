<template>
  <div>
    <h3>Login</h3>

    <form action="#" @submit.prevent>
      <label for="email">
        <input v-model="email" type="text" name="email" placeholder="E-mail">
      </label>
      <br>
      <label for="password">
        <input v-model="password" type="password" name="password" placeholder="Senha">
      </label>
      <br>
      <div v-show="validLogin" style="color: green;">Login validado com sucesso</div>
      <div v-show="message" style="color: red;">Login inválido</div>
      <br>
      <button @click="logar" :disabled="isDisabledAfterSubmit">Logar</button>
    </form>
    <hr>

    <UserList />
  </div>
</template>

<script>
  import UserList from '../UsersList/usersList.vue'

  export default {
    name: 'login',
    components: {
      UserList,
    },
    data () {
      return {
        email: null,
        password: null,
        validLogin: false,
        message: null,
        isDisabledAfterSubmit: false,
      }
    },
    methods: {
      logar () {
        if (this.email && this.password) { // se tudo NÃO esta nulo
          this.isDisabledAfterSubmit = true
          if (this.email.includes('admin') && this.password.includes('asdfasdf')) {
            this.validLogin = true
          } else {
            this.message = 'Login inválido'
            this.validLogin = false
          }
        } else { // se tudo NÃO esta nulo
          this.message = null
          this.validLogin = false
        }

        setTimeout(() => {
          this.isDisabledAfterSubmit = false
        }, 3000)
      }
    }
  }
</script>

<style scoped>
  form {
    display: flex;
    background-color: #CCC;
  }
</style>
