<template>
  <header class="jumbotron">
    <h3>{{ content }}</h3>
  </header>
</template>

<script>
import roles from '@/api/roles'

export default {
  name: 'Admin',
  data() {
    return {
      content: ''
    }
  },
  async created() {
    try {
      const res = await roles.getAdminContent()
      this.content = res.data
    } catch (error) {
      console.log(error.response)
    }
  }
}
</script>
