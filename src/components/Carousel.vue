<template>
  <div
    id="controls"
    class="carousel slide carousel-fade shadow-lg"
    data-ride="carousel"
  >
    <ol class="carousel-indicators">
      <li data-target="#controls" data-slide-to="0" class="active"></li>
      <li data-target="#controls" data-slide-to="1"></li>
    </ol>
    <div class="carousel-inner">
      <div
        class="carousel-item active"
        :style="`background-image: url(${require('@/assets/carousel001.png')})`"
      >
        <div class="jumbotron">
          <p class="lead">
            Welcome to LOOP FOOD CAFE
          </p>
          <h1 class="display-4">Enjoy Our Food Experience</h1>
          <h1>(Yummy Delicious Fast Food)</h1>
          <div class="horizontal my-3">
            <hr class="px-4" />
            <i class="fas fa-utensils"></i>
            <hr class="px-4" />
          </div>
          <p>OPENING HOURS</p>
          <p>
            Sunday - Friday:
            <span>7:00 AM - 9:00 PM</span>
          </p>
          <p>
            Weekends:
            <span>7:00 AM - 9:00 PM</span>
          </p>
          <a
            class="btn btn-primary mt-4 mb-5"
            role="button"
            @click="goto('menu')"
            >SEE MENU</a
          >
        </div>
      </div>
      <div
        class="carousel-item"
        :style="`background-image: url(${require('@/assets/carousel002.png')})`"
      >
        <div class="jumbotron">
          <p class="lead">
            Welcome to LOOP ROOM STUDIO
          </p>
          <h1 class="display-4">Enjoy Our Practice Session</h1>
          <h1>(Before the stage)</h1>
          <div class="horizontal my-3">
            <hr class="px-4" />
            <i class="fas fa-music"></i>
            <hr class="px-4" />
          </div>
          <p>OPENING HOURS</p>
          <p>
            Sunday - Friday:
            <span>7:00 AM - 9:00 PM</span>
          </p>
          <p>
            Weekends:
            <span>7:00 AM - 9:00 PM</span>
          </p>
          <a
            class="btn btn-primary mt-4 mb-5"
            role="button"
            @click="goto('footer')"
            >BOOK RESERSHAL ROOM</a
          >
        </div>
      </div>
    </div>
    <a
      class="carousel-control-prev"
      href="#controls"
      role="button"
      data-slide="prev"
    >
      <!-- <span class="carousel-control-prev-icon" aria-hidden="true"></span> -->
      <!-- <span class="sr-only">Previous</span> -->
      <i class="fas fa-chevron-left"></i>
    </a>
    <a
      class="carousel-control-next"
      href="#controls"
      role="button"
      data-slide="next"
    >
      <!-- <span class="carousel-control-next-icon" aria-hidden="true"></span> -->
      <i class="fas fa-chevron-right"></i>
    </a>
  </div>
</template>

<script>
export default {
  methods: {
    goto(anchor) {
      document.getElementById(anchor).scrollIntoView({
        behavior: "smooth",
        block: "start",
        inline: "start"
      });
    }
  }
};
</script>
<style lang="scss" scoped>
@import "@/colors.scss";

.carousel-control-prev,
.carousel-control-next {
  font-size: 32px;
  color: #fff;
}
p {
  color: #d0d0d0;
  font-weight: 600;
  span {
    font-weight: 400;
  }
}
.carousel {
  margin-top: -64px;
}

.carousel-item {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  .jumbotron {
    text-align: center;
    margin-bottom: 0;
    margin-top: 128px;
    margin-bottom: 32px;
    height: min-content;
    background: transparent;
    width: 100%;
    color: #fff;
    .lead {
      color: $primary;
      font-weight: 600;
    }
  }
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
      margin-left: 16px;
      margin-right: auto;
    }
  }
  i {
    flex: 1;
  }
  svg {
    font-size: 32px !important;
  }
}
</style>
