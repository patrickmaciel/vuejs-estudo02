<template>
  <div>
    <h3>Users List</h3>

    <input type="text" v-model="user">
    <button @click="adicionar">+</button>

    <br>

    <div class="lista">
      <h2>Lista de Usuários</h2>
      <ul>
        <li v-for="item in users" :key="item.id">{{ item.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'usersList',
  data () {
    return {
      user: null,
      users: []
    }
  },
  methods: {
    adicionar () {
      if (this.user) this.users.push({
        id: this.users.length,
        name: this.user
      })
      this.user = null
    }
  }
}
</script>

<style scoped></style>
