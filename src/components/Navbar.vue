<template>
  <nav>
    <div class="logo">
      <a href=""
        ><img src="@/assets/img/logo_rodrigocostas.png" alt="Rodrigo Costas"
      /></a>
    </div>
    <div @click="toggleMenu()" :class="[isOpen ? 'active' : '', 'menu-icon']">
      <span></span>
    </div>
  </nav>
  <Menu @toggle-menu="$emit('toggle-menu', isOpen)" :isOpen="isOpen" />
</template>

<script>
import Menu from "./Menu.vue";
export default {
  name: "Navbar",
  components: {
    Menu,
  },
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
  emits: ["toggle-menu"],
};
</script>

<style scoped>
nav .logo {
  float: left;
  margin-left: 30px;
}

nav .logo a {
  font-size: 28px;
  line-height: 80px;
  text-transform: uppercase;
  color: #fff;
  text-decoration: none;
  letter-spacing: 0.5px;
}

nav .logo img {
  width: 12rem;
}

nav .logo em {
  font-style: normal;
  font-weight: 200;
}

nav {
  background: rgba(255, 255, 255, 1);
  height: 80px;
  position: fixed;
  width: 100%;
  left: 0;
  top: 0;
  z-index: 300;
  box-shadow: 0px 2px 10px 0px rgba(0, 0, 0, 0.5);
}

.menu-icon {
  background: transparent;
  width: 50px;
  height: 50px;
  margin: 15px 39px 0 auto;
  position: relative;
  cursor: pointer;
  transition: background 0.5s;
  border-radius: 5px;
}

.menu-icon span,
.menu-icon span:before,
.menu-icon span:after {
  cursor: pointer;
  border-radius: 1px;
  height: 3px;
  width: 35px;
  background: rgb(0, 0, 0);
  position: absolute;
  left: 15%;
  top: 50%;
  display: block;
  content: "";
  transition: all 0.5s ease-in-out;
}

.menu-icon span:before {
  left: 0;
  top: -10px;
}

.menu-icon span:after {
  left: 0;
  top: 10px;
}

.menu-icon.active {
  background: rgba(250, 250, 250, 0.2);
}

.menu-icon.active span {
  background-color: transparent;
}

.menu-icon.active span:before,
.menu-icon.active span:after {
  top: 0;
}

.menu-icon.active span:before {
  transform: rotate(135deg);
}

.menu-icon.active span:after {
  transform: rotate(-135deg);
}

/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) {
  nav .logo img {
    width: 20rem;
  }
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
  nav .logo img {
    width: 22rem;
  }
}
</style>
