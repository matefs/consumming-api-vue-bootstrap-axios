<template>
   <div class="container">
    <h1>Tabela consultando API</h1>
    <table class="table table-dark table-hover">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Nome</th>
          <th scope="col">Email</th>
          <th scope="col">Cidade</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in usuarios" :key="user.id">
          <th scope="row">#</th>
          <td>{{ user.name }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.address.city }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'dataTable',
  data() {
    return {
      usuarios: String,
    }
  },
  mounted() {
    axios.get("https://jsonplaceholder.typicode.com/users").then((res) => {
      this.usuarios = res.data;
      console.log(res.data);
    });
  },

}
</script>

 