<template>
  <div>
    <h1>Список пользователей</h1>
    <div v-if="!isTableShow">
      Загрузка данных...
    </div>
    <users-list v-else :users="list"></users-list>
  </div>
</template>

<script>
import UsersList from '@/components/UsersList.vue'
import axios from 'axios'

export default {
  name: 'Users',
  components: {
    'users-list': UsersList
  },
  data: function() {
    return {
      list: []
    }
  },
  computed: {
    isTableShow: function() {
      return this.list.length > 0
    }
  },
  created: function() {
    this.loadUsersData()
  },
  methods: {
    loadUsersData() {
      axios
        .get('http://localhost:3004/users')
        .then(response => response.data)
        .then(users => {
          this.list = users
        })
        .catch(error => {
          console.error(error)
        })
    }
  }
}
</script>
