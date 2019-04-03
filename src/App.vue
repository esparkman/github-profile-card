<template>
  <div id="app" class="ui container">
    <h1>My Github Friends</h1>
    <div class="ui cards">
      <GithubUserProfile
        v-for="(username, index) in usernames"
        :key="index"
        :username="username"
      />
    </div>
  </div>
</template>

<script>
import GithubUserProfile from '@/components/GithubUserProfile'
export default {
  name: 'App',
  components: {
    GithubUserProfile
  },
  data() {
    return {
      usernames: ['esparkman', 'gareys', 'wmavis']
    }
  }
}
</script>
