<template>
  <div id="about">
    <div class="container py-4">
      <div class="row">
        <div class="col-12 col-md-7 col-lg-7">
          <p class="highlight mb-1">OUR STORY</p>
          <h1>Welcome To Tisa Restaurant &amp; Espresso</h1>
          <p>Nestled in a peaceful corner, 'Tisa Restaurant &amp; Espresso' is one of the most celebrated restaurants located in Ekantakuna, Lalitpur. Our Restaurant has emerged as one of the major venues, for fine dining with friends & family along with small corporate meetings or other functions. Our menu is never done - we find inspiration all around, in new ingredients, new approaches, and fresh takes on old standards.</p>
          <br />
          <div class="row no-gutters mb-4">
            <div class="col-12 col-sm-6 col-md-12 col-lg-6">
              <ul class="p-0">
                <li>
                  <p>
                    <i class="fas fa-arrow-circle-right"></i> Attentive staffs &amp; stellar experience
                  </p>
                </li>
                <li>
                  <p>
                    <i class="fas fa-arrow-circle-right"></i> Facilities for a disabled person
                  </p>
                </li>
                <li>
                  <p>
                    <i class="fas fa-arrow-circle-right"></i> Fast food and semi-self services
                  </p>
                </li>
              </ul>
            </div>
            <div class="col-12 col-sm-6 col-md-12 col-lg-6">
              <ul class="p-0">
                <li>
                  <p>
                    <i class="fas fa-arrow-circle-right"></i> Free home delivery services
                  </p>
                </li>
                <li>
                  <p>
                    <i class="fas fa-arrow-circle-right"></i> Exclusive business corner place
                  </p>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div
          class="col-12 col-md-5 col-lg-5 tisa"
          :style="`background-image: url(${require('@/assets/wall.jpg')})`"
        ></div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#about {
  // background-image: url(https://morsel.qodeinteractive.com/wp-content/uploads/2017/07/about-us-title-img.jpg);
  background-color: rgba(0, 0, 0, 0.5);
  padding-top: 128px;
}
.highlight {
  font-weight: 600;
  font-size: 14px;
  color: #c5a572;
}

svg {
  color: #c5a572;
}

ul {
  list-style: none;
}

p {
  font-size: 14px;
  line-height: 180%;
}

.tisa {
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  min-height: 328px;
}
</style>