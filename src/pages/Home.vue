<template>
  <main class="home space">
    <h1 style="text-align:center">Converged Networks Project Tracker</h1>
    <LoginSignup v-if="currentUser === null" />
    <div v-else id="greeting">
      <h2>🖐️ Welcome Back {{ currentUser.user_metadata.full_name }}!</h2>
      <p>
        You're logged in. Go check out your
        <router-link :to="{ name: 'journals' }">Projects ➡️ </router-link>.
      </p>
    </div>
    <GithubCorner
      url="https://github.com/chiubaca/vue-netlify-fauna-starter-kit"
    />
  </main>
</template>

<script>
import { mapGetters } from "vuex";
import LoginSignup from "../components/LoginSignup.vue";
import GithubCorner from "../components/GithubCorner.vue";

export default {
  name: "Home",
  components: {
    LoginSignup,
    GithubCorner
  },
  props: {
    msg: String
  },
  data() {
    return {};
  },
  computed: {
    ...mapGetters("auth", ["currentUser"])
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#greeting {
  border-style: dashed;
  padding: 15px;
  border-radius: 15px;
  border-color: #c6c6c6;
  border-width: 1px;
  h2 {
    text-transform: capitalize;
  }
}
img#logo {
  width: 100%;
  height: auto;
}
</style>
