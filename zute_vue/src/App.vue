<template>
<div id="wrapper">
  <nav class="navbar is-warning">
    <div class="navbar-brand">
      <router-link to="/" class="navbar-item"><strong><em>Zute Mart</em></strong></router-link>

      <a class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbar-menu" @click="showMobileMenu = !showMobileMenu">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div class="navbar-menu" id="navbar-menu" v-bind:class="{'is-active': showMobileMenu }">
      <div class="navbar-start">
        <div class="navbar-item">
          <form method="get" action="/search">
            <div class="field has-addons">
              <div class="control">
                <input type="text" class="input" placeholder="What do you need?" name="query">
              </div>
              <div class="control">
                <button class="button is-success">
                  <span class="icon">
                    <i class="fas fa-search"></i>
                  </span>
                </button>
              </div>
            </div>
          </form>

          <div class="dropdown is-hoverable">
            <div class="dropdown-trigger">
              <button class="button" aria-haspopup="true" aria-controls="dropdown-menu4">
                <span><strong>Products</strong></span>
                <span class="icon is-small">
                  <i class="fas fa-angle-down" aria-hidden="true"></i>
                </span>
              </button>
            </div>
            <div class="dropdown-menu" id="dropdown-menu4" role="menu">
              <div class="dropdown-content">
                <div class="dropdown-item">
                  <router-link to="/electronics" class="dropdown-item">Electronics</router-link>
                  <router-link to="/furniture" class="dropdown-item">Furniture</router-link>
                  <router-link to="/groceries" class="dropdown-item">Groceries</router-link>
                  <router-link to="/housing" class="dropdown-item">Housing</router-link>
                  <router-link to="/lifestyle" class="dropdown-item">Lifestyle</router-link>
                </div>
              </div>
            </div>
          </div>

          <router-link to="/about" class="button is-dark"><strong>About</strong></router-link>
        </div>
      </div>
      <div class="navbar-end">

        <div class="navbar-item">
          <div class="buttons">
            <template v-if="$store.state.isAuthenticated">
              <router-link to="/my-account" class="button is-light">My Account</router-link>
            </template>

            <template v-else>
              <router-link to="/sign-up" class="button is-link"><strong>Sign up</strong></router-link>
              <router-link to="/log-in" class="button is-light">Log in</router-link>
            </template>

            <router-link to="/cart" class="button is-success">
              <span class="icon"><i class="fas fa-shopping-cart"></i></span>
              <span>Cart ({{ cartTotalLength }})</span> 
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </nav>

  <div class="is-loading-bar has-text-centered" v-bind:class="{'is-loading': $store.state.isLoading }">
    <div class="lds-dual-ring"></div>
  </div>

  <section class="section">
    <router-view/>
  </section>

  <footer class="footer">
    <p class="has-text-centered">&COPY;ZuteMart 2024</p>
    <div class="content has-text-centered">
      <ol>
        <a class="has-text-dark" href="/about">About Us</a>
        <br>
        <a class="has-text-dark" href="/">Home</a>
        <br>
        <a class="has-text-dark" href="/about">Contact</a>
        <br>
      </ol>
    </div>
  </footer>
</div>
</template>

<script>
import axios from 'axios'
  export default {
    data() {
      return {
        showMobileMenu: false,
        cart: {
          items: []
        }
      }
    },
    beforeCreate() {
      this.$store.commit('initializeStore')

      const token = this.$store.state.token

      if (token) {
        axios.defaults.headers.common['Authorization'] = "Token " + token
      } else {
        axios.defaults.headers.common['Authorization'] = ""
      }
    },
    mounted() {
      this.cart = this.$store.state.cart
    },
    computed: {
      cartTotalLength() {
        let totalLength = 0

        for (let i = 0; i < this.cart.items.length; i++) {
          totalLength += this.cart.items[i].quantity
        }

        return totalLength
      }
    }
  }
</script>

<style lang="scss">
@import '../node_modules/bulma';

.lds-dual-ring {
  display: inline-block;
  width: 80px;
  height: 80px;
}
.lds-dual-ring::after {
  content: " ";
  display: block;
  width: 64px;
  height: 64px;
  margin: 8px;
  border-radius: 50%;
  border: 6px solid #ccc;
  border-color: #ccc transparent;
  animation: lds-dual-ring 1.2s linear infinite;
}
@keyframes lds-dual-ring {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.is-loading-bar {
  height: 0;
  overflow: hidden;

  -webkit-transition: all 0.3s;
  transition: all 0.3s;

  &.is-loading {
    height: 80px;
  }
}
</style>
