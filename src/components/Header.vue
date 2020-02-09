<template>
  <div>
    <nav class="navbar is-origin-color is-fixed-top">
      <div class="navbar-brand">
        <div
          class="navbar-burger burger"
          data-target="navbarExampleTransparentExample"
          :class="{ 'is-active': navActive }"
          @click="toggleBurger()"
        >
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>

      <div
        id="navbarExampleTransparentExample"
        class="navbar-menu"
        :class="{ 'is-active': navActive }"
      >
        <div class="navbar-end">
          <a class="navbar-item" href="#about" @click="closeBurger()">
            <span class="icon">
              <i class="fas fa-info"></i>
            </span>
            <span>About</span>
          </a>
          <!--          <a class="navbar-item" href="#services" @click="closeBurger()">-->
          <!--            <span class="icon">-->
          <!--              <i class="fas fa-bars"></i>-->
          <!--            </span>-->
          <!--            <span>Services</span>-->
          <!--          </a>-->
          <a class="navbar-item" href="#resume" @click="closeBurger()">
            <span class="icon">
              <i class="fas fa-file-alt"></i>
            </span>
            <span>Resume</span>
          </a>
          <a class="navbar-item" href="#portfolio" @click="closeBurger()">
            <span class="icon">
              <i class="fas fa-th-list"></i>
            </span>
            <span>Portfolio</span>
          </a>
          <a class="navbar-item" href="#contact" @click="closeBurger()">
            <span class="icon">
              <i class="fas fa-envelope"></i>
            </span>
            <span>Contact</span>
          </a>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      navActive: false
    }
  },
  methods: {
    toggleBurger() {
      this.navActive = this.navActive !== true
    },
    closeBurger() {
      this.navActive = false
    }
  }
}
</script>

<style scoped></style>
