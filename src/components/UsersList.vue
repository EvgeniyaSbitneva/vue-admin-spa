<template>
  <table class="table table-striped">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Имя</th>
        <th scope="col">Никнейм</th>
        <th scope="col">Email</th>
        <th scope="col">Сайт</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in users" :key="item.id">
        <td>#{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>{{ item.username }}</td>
        <td>{{ item.email }}</td>
        <td>{{ item.website }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'UsersList',
  props: {
    users: {
      type: Array,
      required: true
    }
  }
}
</script>

<style></style>
