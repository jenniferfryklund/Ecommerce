<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary background">
    <div class="container">

      <router-link class="navbar-brand" to="/">
        <i class="fab fa-pagelines p-2"></i>flowershop.se
      </router-link>

      <button
        class="navbar-toggler"
        type="button"
        data-mdb-toggle="collapse"
        data-mdb-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <i class="fas fa-bars"></i>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">

        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link active" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link active" to="/products">Products</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link active" to="/about">About Us</router-link>
          </li>
        </ul>

        <ul class="navbar-nav ms-auto">

          <li class="nav-item dropdown">
            <a
              class="nav-link"
              href="#"
              id="navbarDropdownMenuLink"
              role="button"
              data-mdb-toggle="dropdown"
              aria-expanded="false"
            >
              <i class="fas fa-shopping-cart"></i>
              <span v-show="cartItemCount" class="badge rounded-pill badge-notification bg-danger">{{ cartItemCount }}</span>
            </a>
            <ul class="dropdown-menu dropdown-menu-end shopping-cart" aria-labelledby="navbarDropdownMenuLink">
              <ShoppingCart />
            </ul>
          </li>

          <li class="nav-item dropdown">
            <a
              class="nav-link"
              href="#"
              id="navbarDropdownMenuLink"
              role="button"
              data-mdb-toggle="dropdown"
              aria-expanded="false"
            >
              <i class="fas fa-user"></i>
            </a>
            <ul class="dropdown-menu dropdown-menu-end" aria-labelledby="navbarDropdownMenuLink">
              USER SETTINGS
            </ul>
          </li>

        </ul>

      </div>
    </div>
  </nav>
</template>

<script>
import { mapGetters } from 'vuex'
import ShoppingCart from '../shoppingCart/ShoppingCart'
export default {
  name: 'Navbar',
  components: {
    ShoppingCart
  },
  computed: {
    ...mapGetters(['cartItemCount'])
  }
}
</script>

<style>
.background {
  background-color: rgb(93, 37, 182) !important;
}
.shopping-cart {
  min-width: 450px;
}
.fa-shopping-cart {
  color: #fff;
}
.fa-user {
  color: #fff;
}
</style>