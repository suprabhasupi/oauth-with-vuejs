<template>
  <div class="container">
    <div class="row align-items-center profile-header">
      <button @click="logout">Log out Profile</button>
      <div class="col-md-2 mb-3">
        <img
          :src="$auth.user.picture"
          alt="User's profile picture"
          class="rounded-circle img-fluid profile-picture"
        />
      </div>
      <div class="col-md text-center text-md-left">
        <h2>{{ $auth.user.name }}</h2>
        <p class="lead text-muted">{{ $auth.user.email }}</p>
      </div>
    </div>

    <div class="row">
      <pre>{{JSON.stringify($auth.user, null, 2)}}</pre>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Profile',
  created() {
    // let authUser = this.$auth.user;
    // console.log("authUser---->>>>", authUser)
  },
  methods: {
    logout() {
      console.log("handleLogout", this.$auth)
      this.$auth.logout({
        returnTo: window.location.origin
      })
    }
  }

}
</script>