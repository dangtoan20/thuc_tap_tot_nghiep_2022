<template>
  <nav class="navbar navbar-expand-lg navbar-dark ftco_navbar bg-dark ftco-navbar-light scrolled awake" id="ftco-navbar">
    <div class="container">
      <nuxt-link to="/" class="navbar-brand nuxt-link-active" style="color: #82ae46;">Vegefoods</nuxt-link>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#ftco-nav" aria-controls="ftco-nav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="oi oi-menu"></span> Menu
      </button>

      <div class="collapse navbar-collapse" id="ftco-nav">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <nuxt-link to="/" class="nav-link nav-hover">Home</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link to="/shop" class="nav-link">Shop</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link to="/" class="nav-link">About</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link to="/" class="nav-link">Blog</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link to="/" class="nav-link">Contact</nuxt-link>
          </li>
          <li class="nav-item cta-colored">
            <nuxt-link class="nav-link" :to="{ name: 'cart' }">
              <span class="icon-shopping_cart"></span>
              <span  v-if="cartQuantity > 0">[{{ cartQuantity }}]</span>
            </nuxt-link>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="dropdown04" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">My Accout</a>
            <div class="dropdown-menu" aria-labelledby="dropdown04" v-if="this.$store.state.user.token !== null">
              <a href="" class="dropdown-item">{{ getUser.name }}</a>
              <a href="#" class="dropdown-item" @click="logout">Logout</a>
            </div>

            <div class="dropdown-menu" aria-labelledby="dropdown04" v-if="this.$store.state.user.token == null">
              <nuxt-link to="/login" class="dropdown-item">Login</nuxt-link>
              <nuxt-link to="/register" class="dropdown-item">Register</nuxt-link>
            </div>

<!--            <div class="dropdown-menu" aria-labelledby="dropdown04">-->
<!--              <nuxt-link to="/login" class="dropdown-item" v-show="this.$store.state.user.token">Login</nuxt-link>-->
<!--              <a href="#" class="dropdown-item" v-show="this.$store.state.user.token !== null" @click="logout">Logout</a>-->
<!--            </div>-->
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
<script>
import { mapGetters } from 'vuex'
export default {
  name: 'UserNavbar',
  computed: {
    ...mapGetters(['cartQuantity', 'getUser']),

  },
  methods: {
    logout() {
      this.$store.dispatch('logout')
    },
  },
}
</script>
