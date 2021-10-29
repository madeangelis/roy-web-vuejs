<template>
  <div :class="[isOpen ? 'open' : '', 'overlay-menu']">
    <div class="container">
      <div class="row">
        <div class="main-menu">
          <ul>
            <li>
              <a href="about.html">Biografía</a>
            </li>
            <li>
              <a href="retro.html">Retro</a>
            </li>
            <li>
              <!-- Modal button -->
              <button id="modBtn" class="modal-btn">Contacto</button>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Menu",
  props: {
    isOpen: Object,
  },
};
</script>

<style scoped>
.overlay-menu {
  background: rgba(0, 0, 0, 0.95);
  color: #ffffff;
  position: fixed;
  z-index: 100;
  left: 0;
  top: 0;
  height: 100%;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
  width: 100%;
  padding: 50px 0;
  opacity: 0;
  text-align: center;
  transform: translateY(-100%);
  transition: all 0.5s;
}

.overlay-menu.open {
  opacity: 1;
  transform: translateY(0%);
}

.overlay-menu .main-menu {
  transform: translateY(50%);
  opacity: 0;
  transition: all 0.3s;
  transition-delay: 0s;
}

.overlay-menu.open .main-menu {
  transition: all 0.7s;
  transition-delay: 0.7s;
  opacity: 1;
  transform: translateY(0%);
}

.overlay-menu .main-menu:nth-child(2) {
  transition-delay: 0s;
}

.overlay-menu.open .main-menu:nth-child(2) {
  transition-delay: 1.25s;
}

.overlay-menu {
  overflow: scroll;
}

.overlay-menu::-webkit-scrollbar {
  display: none;
}

.overlay-menu ul {
  list-style: none;
  margin-top: 80px;
  padding: 0px;
}
.overlay-menu ul li {
  padding: 15px 0px;
  font-family: "Open Sans";
}

.overlay-menu ul li a,
.overlay-menu ul li button {
  font-size: 24px;
  font-weight: 300;
  color: #fff;
  text-decoration: none;
  transition: all 0.5s;
}

.overlay-menu ul li a:hover,
.overlay-menu ul li button:hover {
  color: rgba(250, 250, 250, 0.5);
}

.overlay-menu ul li button {
  background-color: transparent;
  border: none;
}

.overlay-menu ul li button:focus {
  outline: none;
}

.overlay-menu p {
  margin-top: 60px;
  font-size: 13px;
  text-transform: uppercase;
  color: #fff;
  font-weight: 200;
  letter-spacing: 0.5px;
  text-align: center;
}
</style>
