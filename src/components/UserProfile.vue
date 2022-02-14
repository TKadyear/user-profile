<template>
  <div class="container">
    <img :src="user.avatar_url" :alt="user.name" />
    <p class="user-name">{{ user.name }}</p>
    <p class="text-gray-400">Joined in {{ user.created_at }}</p>
    <p>{{ user.bio }}</p>
    <hr />
    <p class="text-gray-400">{{ user.following }} Friends</p>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'UserProfile',
  props: {
    username: { type: String, required: true }
  },
  data() {
    return {
      user: {}
    }
  },
  async created() {
    const response = await axios.get(`https://api.github.com/users/${this.username}`)
    this.user = response.data
  }
}
</script>
<style scoped>
.container {
  @apply w-80 rounded-xl;
  box-shadow: 0 4px 8px 4px #00000050;
  transition: 500ms;
}
.container:hover {
  transform: scale(1.1);
}
.container > img {
  @apply w-80 rounded-t-xl;
}
.user-name {
  @apply font-bold text-xl;
}
</style>
