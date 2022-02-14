<template>
  <main class="w-3/4 m-auto grid grid-cols-3 gap-4">
    <UserProfile v-for="user in listUserNames" :key="user" :username="user" />
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
      listUserNames: ['mojombo', 'defunkt', 'pjhyett', 'wycats', 'ezmobius', 'ivey']
    }
  }
}
</script>

<style>
</style>
