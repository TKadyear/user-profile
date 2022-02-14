<template>
  <main class="w-3/4 m-auto grid grid-cols-3 gap-4">
    <UserProfile v-for="user in listUserNames" :key="user" :username="user" />
  </main>
</template>

<script>
import axios from 'axios'
import UserProfile from './components/UserProfile.vue'
export default {
  components: {
    UserProfile
  },
  data() {
    return {
      listUserNames: ["mojombo", "defunkt", "pjhyett", "wycats", "ezmobius", "ivey"]
    }
  },
  async created() {
    const response = await axios.get('https://api.github.com/users')
    const data = response.data
    for (const i in data) {
      this.listUserNames.push(data[i].login)
    }
  }
}
</script>

<style>
</style>
