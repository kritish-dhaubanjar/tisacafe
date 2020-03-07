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
              <h4 class="mt-5 mb-3">Pasta &amp; Spaghetti</h4>
              <ul>
                <li v-for="item in pasta" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5">Sizzler</h4>
              <ul>
                <li v-for="item in sizzler" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Biryani</h4>
              <ul>
                <li v-for="item in biryani" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Syabhale</h4>
              <ul>
                <li v-for="item in syabhale" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Khaja Set</h4>
              <ul>
                <li v-for="item in khaja" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Meat Ball</h4>
              <ul>
                <li v-for="item in meat" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Buff Items</h4>
              <ul>
                <li v-for="item in buff" :key="item.name">
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
              <h4 class="mt-5 mb-3">Chicken Items</h4>
              <ul>
                <li v-for="item in chicken" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Newari Items</h4>
              <ul>
                <li v-for="item in newari" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Fried Items</h4>
              <ul>
                <div class="d-flex" style="justify-content: flex-end;">
                  <h6 class="mb-3">1 pc</h6>
                  <h6 class="mb-3 ml-1">2 pcs</h6>
                  <h6 class="mb-3 ml-1">8 pcs</h6>
                </div>
                <li v-for="item in fried" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>
                    <span class="ml-2" v-for="(rate,index) in item.price" :key="index">{{rate}}</span>
                  </p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Veg Snacks</h4>
              <ul>
                <li v-for="item in veg" :key="item.name">
                  <p>{{item.name}}</p>
                  <hr class="mx-1" />
                  <p>{{item.price}}</p>
                </li>
              </ul>
            </div>
            <div class="col-12">
              <h4 class="mt-5 mb-3">Salad</h4>
              <ul>
                <li v-for="item in salad" :key="item.name">
                  <p>{{item.name}}</p>
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
import {
  pasta,
  sizzler,
  biryani,
  syabhale,
  khaja,
  meat,
  buff,
  chicken,
  newari,
  fried,
  veg,
  salad
} from "./../../assets/lunch/lunch";
export default {
  data() {
    return {
      pasta,
      sizzler,
      biryani,
      syabhale,
      khaja,
      meat,
      buff,
      chicken,
      newari,
      fried,
      veg,
      salad
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