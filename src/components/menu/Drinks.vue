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
              <h4 class="mt-5 mb-3">Cold Beverage</h4>
              <ul>
                <li v-for="item in cold" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Beer</h4>
              <ul>
                <li v-for="item in beer" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>

              <h4 class="mt-5 mb-3">Wine</h4>
              <ul>
                <li v-for="item in wine" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-6">
          <div class="row no-gutters">
            <div class="col-12">
              <ul>
                <li style="justify-content:space-between;">
                  <h4 class="p-0 mt-5 mb-0">Liquor</h4>
                  <div class="d-flex" style="align-items: flex-end;">
                    <h6 class="mt-5 mr-5 mb-0">30ml</h6>
                    <h6 class="mt-5 mb-0">60ml</h6>
                  </div>
                </li>
              </ul>
              <ul>
                <li v-for="item in liquor" :key="item.name">
                  <div>
                    <p>{{item.name}}</p>
                  </div>
                  <hr class="mx-1" />
                  <p class="mr-5">{{item.price[0]}}</p>
                  <p>{{item.price[1]}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Hookah/Cigerattes</h4>
              <ul>
                <li v-for="item in hookah" :key="item.name">
                  <div>
                    <p>{{item.name}}</p>
                    <p class="small" v-html="item.detail"></p>
                  </div>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
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
import { cold, beer, wine, hookah, liquor } from "./../../assets/drinks/drinks";
export default {
  data() {
    return {
      cold,
      wine,
      beer,
      hookah,
      liquor
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

.dark {
  background-color: rgba(31, 31, 31, 0.9) !important;
  color: #fff;
  h4 {
    color: #dc3545;
  }
  li {
    color: #fff;
  }
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