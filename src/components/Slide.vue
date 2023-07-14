<template>
  <div class="backdrop" @click="$emit('hideMenu')">
    <div class="menu">
      <i class="fas fa-times"></i>
      <ul class="p-0">
        <li>
          <a @click="go('controls')">HOME</a>
        </li>
        <li>
          <a @click="go('menu')">MENU</a>
        </li>
        <li>
          <a @click="go('about')">ABOUT US</a>
        </li>
        <li>
          <a @click="go('footer')">CONTACT US</a>
        </li>
        <li>
          <a @click="go('footer')">BOOK REHERSHAL ROOM</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    go(anchor) {
      document.getElementById(anchor).scrollIntoView({
        behavior: "smooth",
        block: "start",
        inline: "start"
      });
    }
  }
};
</script>

<style scoped lang="scss">
.backdrop {
  position: fixed;
  top: 0;
  height: 100vh;
  z-index: 1024;
  background-color: rgba(0, 0, 0, 0.9);
  scroll-behavior: unset;
  width: 100vw;
  display: flex;
}

.menu {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  svg {
    position: fixed;
    font-size: 24px;
    margin-top: 16px;
    margin-right: 16px;
    color: #fff;
    right: 0;
    top: 0;
  }
}

ul {
  list-style: none;
  text-align: center;
  li {
    color: #fff;
    font-weight: 600;
    padding-top: 8px;
    padding-bottom: 8px;
  }
}
</style>
