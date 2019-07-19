<template>
  <div>
    <div v-if="!isTableShow">
      Загрузка данных...
    </div>
    <users-list v-else :users="list"></users-list>
  </div>
</template>

<script>
import UsersList from '@/components/UsersList.vue'

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
  }
}
</script>
