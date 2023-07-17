<template>
  <div>
    <div class="wave-holder pb-3">
      <div class="wave" />
    </div>

    <div class="container-fluid">
      <div class="row">
        <div class="col-12 col-md-6">
          <div class="row no-gutters">
            <div class="col-12">
              <h4 class="mt-5">Mo: Mo</h4>

              <ul>
                <div class="d-flex" style="justify-content: flex-end;">
                  <h6 class="mb-3">Steam</h6>
                  <h6 class="mb-3 ml-1">Fried</h6>
                  <h6 class="mb-3 ml-1">Kothey</h6>
                  <h6 class="mb-3 ml-1">C</h6>
                </div>
                <li v-for="item in momo" :key="item.name">
                  <div>
                    <p>{{ item.name }}</p>
                    <p class="small" v-html="item.detail"></p>
                  </div>
                  <hr class="mx-1" />
                  <p>
                    <span class="ml-2" v-for="(rate, index) in item.price" :key="index">{{ rate }}</span>
                  </p>
                </li>
              </ul>
            </div>

            <div class="col-12">
              <h4 class="mt-5 mb-3">Chowmein</h4>
              <ul>
                <li v-for="item in chowmein" :key="item.name">
                  <p>{{ item.name }}</p>
                  <hr class="mx-1" />
                  <p>{{ item.price }}</p>
                </li>
              </ul>
            </div>

            <div class="col-12">
              <h4 class="mt-5 mb-3">Veg Snacks</h4>
              <ul>
                <li v-for="item in veg" :key="item.name">
                  <p>{{ item.name }}</p>
                  <hr class="mx-1" />
                  <p>{{ item.price }}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Non Veg Snacks</h4>
              <ul>
                <li v-for="item in nonVeg" :key="item.name">
                  <p>{{ item.name }}</p>
                  <hr class="mx-1" />
                  <p>{{ item.price }}</p>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <div class="col-12 col-md-6">
          <div class="row no-gutters">
            <div class="col-12">
              <h4 class="mt-5 mb-3">Fried Rice</h4>
              <ul>
                <li v-for="item in rice" :key="item.name">
                  <p>{{ item.name }}</p>
                  <hr class="mx-1" />
                  <p>{{ item.price }}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Burger (Scheduled after opening)</h4>
              <ul>
                <li v-for="item in burger" :key="item.name">
                  <p>{{ item.name }}</p>
                  <hr class="mx-1" />
                  <p>{{ item.price }}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Stick Items</h4>
              <ul>
                <div class="d-flex" style="justify-content: flex-end;">
                  <h6 class="mb-3">1 pc</h6>
                  <!-- <h6 class="mb-3 ml-1">2 pcs</h6> -->
                  <!-- <h6 class="mb-3 ml-1">8 pcs</h6> -->
                </div>
                <li v-for="item in fried" :key="item.name">
                  <p>{{ item.name }}</p>
                  <hr class="mx-1" />
                  <p>
                    <span class="ml-2" v-for="(rate, index) in item.price" :key="index">{{ rate }}</span>
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
import {
  soup,
  momo,
  soupmomo,
  chowmein,
  thukpa,
  rice,
  burger,
  roll,
  chopsuey,
  pizza,
  veg,
  fried,
  nonVeg
} from "./../../assets/lunch/lunch";
export default {
  data() {
    return {
      soup,
      momo,
      soupmomo,
      chowmein,
      thukpa,
      rice,
      burger,
      roll,
      chopsuey,
      pizza,
      veg,
      fried,
      nonVeg
    };
  }
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
