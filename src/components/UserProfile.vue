<template>
  <div class="container">
    <img :src="username.avatar_url" :alt="username.name" />
    <p class="user-name">{{ username.name }}</p>
    <p class="text-gray-400">Joined in {{ username.created_at }}</p>
    <p>{{ username.bio }}</p>
    <hr />
    <p class="text-gray-400">{{ username.following }} Friends</p>
  </div>
</template>
<script>
export default {
  name: 'UserProfile',
  props: {
    username: { type: Object, required: true }
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
