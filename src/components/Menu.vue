
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
            <div v-for="(menu, index) in menus" :key="menu.name" class="col-4 col-sm-3 col-md-2" @click="showMenu(index)"
              :class="active == index ? 'active' : ''">
              <div class="card shadow-lg">
                <div class="card-body">
                  <i :class="menu.icon"></i>
                  <p>{{ menu.name }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <transition v-if="menus[active]" enter-active-class="animated fadeIn" leave-active-class="animated fadeOut"
        mode="out-in">
        <Menu :key="active" :menu="menus[active]" />
      </transition>
    </div>
  </div>
</template>

<script>
import Menu from "@/components/menu/Menu";
export default {
  data() {
    return {
      menus: [],
      active: 0,
    };
  },
  methods: {
    showMenu(pos) {
      this.active = pos;
    }
  },

  async beforeMount() {
    const [{ entries: types }, { entries: categories }, { entries: menus }] = await Promise.all([
      fetch('https://api.loopstudiocafe.com/api/collections/get/types').then((res) => res.json()),
      fetch('https://api.loopstudiocafe.com/api/collections/get/categories').then((res => res.json())),
      fetch('https://api.loopstudiocafe.com/api/collections/get/menu').then((res) => res.json()),
    ])

    const menu = types.map(({ name, icon }) => {
      const categoryNames = categories.filter((category) => category.type.display === name).map(({ name }) => name);

      const menuCategory = categoryNames.reduce((acc, categoryName) => {
        const menuItems = menus.filter((menu) => menu.category.display === categoryName)

        if (!acc[categoryName]) {
          acc[categoryName] = []
        }

        menuItems.forEach(({ name, prices, types }) => {
          acc[categoryName].push({
            name,
            types,
            prices
          })
        })

        return acc;
      }, {})

      return {
        name,
        icon,
        categoryNames,
        menuCategory
      }
    })

    this.menus = menu;
  },

  components: {
    Menu
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
    justify-content: space-around;
  }
}
</style>
