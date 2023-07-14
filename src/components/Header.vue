<template>
  <nav class="navbar navbar-expand-sm navbar-dark shadow-md" :class="stick? 'over': ''">
    <a class="navbar-brand m-0" href="#">
      <img src="./../assets/tisa.png" width="35" height="35" alt />
      Loop
      <span class="d-none d-sm-none d-md-inline-block pl-1">Studio Cafe</span>
    </a>
    <span class="navbar-toggler" data-toggle="collapse" aria-expanded="false" @click="showMenu">
      <!-- <span class="navbar-toggler-icon" @click="showMenu"></span> -->
      <i class="fas fa-bars"></i>
    </span>

    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto ml-auto">
        <li class="nav-item">
          <a class="nav-link" @click="go('controls')" :class="active=='controls' ? 'active': ''">
            <span class="spanLeft">[&nbsp;</span>HOME
            <span class="spanRight">]</span>
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" @click="go('about')" :class="active=='about' ? 'active': ''">
            <span class="spanLeft">[</span>&nbsp;ABOUT US
            <span class="spanRight">]</span>
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" @click="go('menu')" :class="active=='menu' ? 'active': ''">
            <span class="spanLeft">[</span>&nbsp;MENU
            <span class="spanRight">]</span>
          </a>
        </li>

        <li class="nav-item">
          <a class="nav-link" @click="go('footer')" :class="active=='footer' ? 'active': ''">
            <span class="spanLeft">[</span>&nbsp;CONTACT US
            <span class="spanRight">]</span>
          </a>
        </li>

        <li class="nav-item">
          <a class="nav-link" @click="go('footer')" :class="active=='footer' ? 'active': ''">
            <span class="spanLeft">[</span>&nbsp;BOOK REHERSHAL ROOM
            <span class="spanRight">]</span>
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      stick: false,
      active: "controls"
    };
  },
  name: "Header",

  methods: {
    go(anchor) {
      this.active = anchor;
      document.getElementById(anchor).scrollIntoView({
        behavior: "smooth",
        block: "start",
        inline: "start"
      });
    },

    showMenu() {
      document.body.classList.add("noscroll");
      this.$emit("showMenu");
    }
  },

  beforeCreate() {
    window.onscroll = () => {
      let y = document.getElementById("controls").getClientRects()[0].y;
      if (y < -360 && !this.stick) {
        this.stick = true;
      } else if (y > -360 && y != 0 && this.stick) {
        this.stick = false;
      }
    };
  }
};
</script>

<style lang="scss" scoped>
nav {
  background-color: transparent;
  z-index: 1000;
  .navbar-brand {
    font-family: "Bellefair";
    font-weight: 600;
    font-size: 21px;
    font-weight: 500;
    display: flex;
    align-items: center;
    img {
      margin-right: 4px;
    }
  }
}
.spanLeft {
  transition: 250ms;
  position: relative;
  left: -4px;
  opacity: 0;
  color: #c5a572;
}
.spanRight {
  transition: 250ms;
  position: relative;
  right: -4px;
  opacity: 0;
  color: #c5a572;
}

.over {
  // background-color: rgba(1, 14, 26, 1);
  background: #fff;
  .navbar-brand {
    color: #1f2438;
  }
  .nav-link {
    color: #1f2438 !important;
    transition: 250ms;

    &:hover {
      transition: 250ms;
      color: #c5a572 !important;
      .spanLeft {
        position: relative;
        left: 0px;
        opacity: 1;
      }
      .spanRight {
        position: relative;
        right: 0px;
        opacity: 1;
      }
    }
  }
  transition: 500ms ease-out;
  opacity: 1;
  position: sticky;
  top: 0;
  border-bottom: 1px solid rgba(102, 102, 102, 0.25);
  box-shadow: 0 1rem 3rem rgba(0, 0, 0, 0.175) !important;
  .navbar-toggler {
    color: #1f2438;
  }
}

.nav-item {
  .nav-link {
    font-size: 14px;
    color: #fff;
    padding: 0px 24px !important;
    font-family: "Montserrat";
    font-weight: bold;
    transition: 250ms;
    &:hover {
      transition: 250ms;
      color: #c5a572;
      .spanLeft {
        position: relative;
        left: 0px;
        opacity: 1;
      }
      .spanRight {
        position: relative;
        right: 0px;
        opacity: 1;
      }
    }
  }
  .active {
    color: #c5a572 !important;
    .spanLeft {
      position: relative;
      left: 0px;
      opacity: 1;
    }
    .spanRight {
      position: relative;
      right: 0px;
      opacity: 1;
    }
  }
}

.navbar-toggler {
  border: 0 !important;
}
a {
  cursor: pointer;
}

@media screen and(min-width: 1200px) {
  .navbar-brand {
    position: absolute;
  }

  .navbar {
    padding-top: 18px;
    padding-bottom: 18px;
  }
}

.navbar-toggler {
  color: #fff;
}

@media screen and(max-width: 856px) {
  .nav-item .nav-link {
    padding-right: 0 !important;
  }
}
</style>
