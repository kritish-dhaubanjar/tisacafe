<template>
  <div>
    <div class="wave-holder pb-3">
      <div class="wave" />
    </div>

    <div class="container-fluid">
      <div class="row">
        <div class="col-12">
          <div class="row no-gutters">
            <div v-for="categoryName of menu.categoryNames" :key="categoryName" class="col-12 col-md-6">
              <h4 class="mt-5">{{ categoryName }}</h4>
              <ul>
                <div class="d-flex" style="justify-content: flex-end;">
                  <h6 class="mb-3" v-for="(type, index) in  menu.menuCategory[categoryName][0].types " :key="type"
                    :class="{ 'ml-1': index > 0 }">{{ type }}</h6>
                </div>

                <li v-for="item in menu.menuCategory[categoryName]" :key="item.name">
                  <div>
                    <p>{{ item.name }}</p>
                  </div>
                  <hr class="mx-1" />
                  <p>
                    <span class="ml-2" v-for="(rate, index) in item.prices" :key="index">{{ rate }}</span>
                  </p>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="wave-holder pb-3">
      <div class="wave-bottom" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["menu"],
};
</script>

<style scoped lang="scss">
h4,
h6 {
  color: #bd2130;
}

ul {
  list-style-type: none;
  padding-left: 0;
}

li {
  font-family: "Kreon", serif;
  display: flex;
  color: #3d3d3d;

  p {
    min-width: max-content;
    margin-bottom: 4px;
  }

  hr {
    border-top: 2px dotted #a1a1a1;
    margin-bottom: 4px;

    width: 100%;
  }
}

@media screen and(min-width: 768px) {
  h4 {
    padding-left: 48px;
  }

  ul {
    padding-right: 64px;
    padding-left: 64px;
  }
}

.container-fluid {
  background-color: rgba(255, 255, 255, 0.9) !important;
}

@media screen and(max-width: 767px) {
  h4 {
    padding-left: 8px;
  }

  ul {
    padding-right: 16px;
    padding-left: 16px;
  }
}

.wave-holder {
  background-color: rgba(255, 255, 255, 0.9);
}

.wave {
  background-image: url("~@/assets/border-wave.svg");
  background-repeat: repeat-x;
  height: 8px;
  position: relative;
  top: -7px;
}

.wave-bottom {
  background-image: url("~@/assets/border-wave.svg");
  background-repeat: repeat-x;
  height: 14px;
  position: relative;
  top: 22px;
  z-index: 0;
}
</style>
