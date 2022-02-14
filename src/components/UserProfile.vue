<template>
  <div class="container">
    <img :src="imageUserProfile" :alt="nameUser" />
    <p class="user-name">{{ nameUser }}</p>
    <p class="text-gray-400">Joined in {{ since }}</p>
    <p>{{ description }}</p>
    <hr />
    <p class="text-gray-400">{{ numberFriends }} Friends</p>
  </div>
</template>
<script>
export default {
  name: 'BoilerPlate',
  props: {
    nameUser: { type: String, required: true },
    imageUserProfile: { type: String, required: true },
    since: { type: String, required: true },
    description: { type: String, required: true },
    numberFriends: { type: String, required: true }
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
