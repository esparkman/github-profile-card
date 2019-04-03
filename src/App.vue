<template>
  <div id="app" class="ui container">
    <h1>Listeneers of 2019</h1>
    <div class="ui cards">
      <GithubUserProfile v-for="(username, index) in usernames" :username="username" :key="index"/>
    </div>
  </div>
</template>

<script>
import GithubUserProfile from "@/components/GithubUserProfile";
export default {
  name: "App",
  components: {
    GithubUserProfile
  },
  data() {
    return {
      usernames: [
        "ssickles",
        "esparkman",
        "ealdent",
        "iangawronski",
        "wmavis",
        "huntermeyer",
        "david-frederick",
        "claycribbs",
        "dborchert",
        "jmscholen"
      ]
    };
  }
};
</script>
