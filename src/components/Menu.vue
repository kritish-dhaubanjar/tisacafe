<template>
  <div id="menu" class="pt-5">
    <div class="container pb-5">
      <div class="row">
        <div class="col-12 text-center">
          <p class="highlight mb-1 mt-5 pt-5">FOOD AT FIRST SIGHT</p>
          <h1>Our Cafe Menu</h1>
          <div class="horizontal">
            <hr class="px-4" />
            <i class="fas fa-utensils"></i>
            <hr class="px-4" />
          </div>
          <div class="row no-gutters mt-5 mb-5 pb-3">
            <div
              class="col-4 col-sm-3 col-md-2"
              @click="showMenu(0)"
              :class="menus.indexOf(current) == 0 ? 'active' : ''"
            >
              <div class="card shadow-lg">
                <div class="card-body">
                  <i class="fas fa-pizza-slice"></i>
                  <p>Fast Food</p>
                </div>
              </div>
            </div>
            <div
              class="col-4 col-sm-3 col-md-2"
              @click="showMenu(1)"
              :class="menus.indexOf(current) == 1 ? 'active' : ''"
            >
              <div class="card shadow-lg">
                <div class="card-body">
                  <i class="fas fa-utensils"></i>
                  <p>Lunch</p>
                </div>
              </div>
            </div>
            <div
              class="col-4 col-sm-3 col-md-2"
              @click="showMenu(2)"
              :class="menus.indexOf(current) == 2 ? 'active' : ''"
            >
              <div class="card shadow-lg">
                <div class="card-body">
                  <i class="fas fa-mug-hot"></i>
                  <p>Tea &amp; Coffee</p>
                </div>
              </div>
            </div>
            <div
              class="col-4 col-sm-3 col-md-2"
              @click="showMenu(3)"
              :class="menus.indexOf(current) == 3 ? 'active' : ''"
            >
              <div class="card shadow-lg">
                <div class="card-body">
                  <i class="fas fa-glass-whiskey"></i>
                  <p>Refreshers</p>
                </div>
              </div>
            </div>
            <div
              class="col-4 col-sm-3 col-md-2"
              @click="showMenu(4)"
              :class="menus.indexOf(current) == 4 ? 'active' : ''"
            >
              <div class="card shadow-lg">
                <div class="card-body">
                  <i class="fas fa-glass-cheers"></i>
                  <p>Bar Drinks</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <transition
        enter-active-class="animated fadeIn"
        leave-active-class="animated fadeOut"
        mode="out-in"
      >
        <component :is="current" />
      </transition>
    </div>
  </div>
</template>

<script>
import Drinks from "@/components/menu/Drinks";
import Coffee from "@/components/menu/Coffee";
import Lunch from "@/components/menu/Lunch";
import LunchII from "@/components/menu/LunchII";
import Refresh from "@/components/menu/Refresh";
export default {
  data() {
    return {
      current: Lunch,
      menus: [Lunch, LunchII, Coffee, Refresh, Drinks]
    };
  },
  methods: {
    showMenu(pos) {
      this.current = this.menus[pos];
    }
  },

  components: {
    Drinks,
    Coffee,
    Lunch,
    Refresh
  }
};
</script>

<style lang="scss" scoped>
@import "~@/colors.scss";

#menu {
  background-color: rgba(0, 0, 0, 0.5);
  padding-bottom: 128px;
}
.card {
  transition: 500ms;
  &:hover {
    background-color: #f2ea49;
    cursor: pointer;
    svg,
    p {
      color: #000;
    }
  }
  border: 1px solid #c5a572;
  background: transparent;
}
.card-body {
  padding: 24px 4px;

  svg {
    font-size: 32px;
  }
  p {
    color: #fff;
    font-weight: 500;
    margin-top: 8px;
    margin-bottom: 0;
  }
}

.highlight {
  font-weight: 600;
  font-size: 14px;
  color: #f2ea49;
}

svg {
  color: #f2ea49;
}

ul {
  list-style: none;
}

p {
  font-size: 14px;
  line-height: 180%;
}

.horizontal {
  display: flex;
  align-items: center;

  hr {
    border-top: 1px solid $primary;

    &:first-child {
      width: 10vw;
      margin-right: 16px;
      margin-left: auto;
    }
    &:last-child {
      width: 10vw;
      margin-right: auto;
      margin-left: 16px;
    }
  }
  i {
    flex: 1;
  }
  svg {
    font-size: 32px !important;
  }
}

.active {
  background-color: #f2ea49;
  svg,
  p {
    color: #000;
  }
}

@media screen and (min-width: 768px) {
  .no-gutters {
    display: flex;
    justify-content: space-between;
  }
}
</style>
