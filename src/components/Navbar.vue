<template>
  <nav id="nav" :class="{ active: isActive }">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
  <button class="nav-button card" @click="toggleNav()">
    <span></span>
    <span></span>
    <span></span>
  </button>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    toggleNav() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style lang="scss">
#nav {
  // Positioning
  position: fixed;
  right: -30vw;
  top: 0;
  bottom: 0;
  // Layout
  display: flex;
  flex-direction: column;
  width: 30vw;
  padding: 10px 30px;
  gap: 20px;
  background: var(--svg-fill);
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  z-index: 100;
  // transition: right 0.5s cubic-bezier(0.77, 0.2, 0.21, 1.68);
  transition: right 0.3s ease-in-out;
  padding: 20px;

  &.active {
    right: 0;
  }

  &::after {
    content: "";
    position: absolute;
    top: 5px;
    left: 5px;
    right: 5px;
    bottom: 5px;
    border: 2px solid rgb(232, 231, 231);
    z-index: -1;
  }

  a {
    // background: white;
    color: rgb(232, 231, 231);
    text-decoration: none;
    font-family: "Arima Madurai", cursive;
    border: 2px solid transparent;
    padding: 10px;
    transition: all 0.3s ease-in-out;

    &:hover {
      border: 2px solid rgb(232, 231, 231);
    }

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.nav-button.card {
  position: fixed;
  top: 10px;
  right: 10px;
  // margin: 0;
  // padding: 0;
  border: none;
  // background: none;
  z-index: 110;

  span {
    width: 16px;
    height: 2px;
    background: white;
    display: block;
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);

    &:not(:last-child) {
      margin-bottom: 4px;
    }
  }
}
</style>
