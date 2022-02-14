<template>
  <main class="w-3/4 m-auto grid grid-cols-3">
    <UserProfile
      :nameUser="user.name"
      :imageUserProfile="user.avatar_url"
      :since="user.created_at"
      :description="user.bio"
      :numberFriends="user.following"
    />
  </main>
</template>

<script>
import UserProfile from './components/UserProfile.vue'
export default {
  components: {
    UserProfile
  },
  data() {
    return {
      user: {}
    }
  },
  created() {
    fetch('https://api.github.com/users/mojombo')
      .then(response => response.json())
      .then(data => {
        let fullYear = new Date(data.created_at)
        fullYear = fullYear.getFullYear()
        data.created_at = fullYear
        this.user = data
      })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
