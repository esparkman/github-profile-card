<template>
  <div class="ui card">
    <div class="image">
      <img :src="user.avatar_url" />
    </div>
    <div class="content">
      <a :href="`https://github.com/${username}`" class="header">{{
        user.name || 'Name Less'
      }}</a>
      <div class="meta">
        <span class="date">
          Joined Github in {{ user.created_at | joinYear }}
        </span>
      </div>
      <div class="description">{{ user.bio }}</div>
    </div>
    <div class="extra content">
      <a :href="`https://github.com/${username}/followers`">
        <i class="user icon"></i>
        {{ user.followers }} Followers
      </a>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import moment from 'moment'
export default {
  name: 'GithubUserProfile',
  filters: {
    joinYear(date) {
      return moment(date).format('YYYY')
    }
  },
  props: {
    username: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      user: {}
    }
  },
  created() {
    axios
      .get(`https://api.github.com/users/${this.username}`)
      .then(response => {
        this.user = response.data
      })
  }
}
</script>
