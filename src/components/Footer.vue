<template>
  <div id="footer">
    <div class="wrapper">
      <div class="container pt-5">
        <div class="row">
          <div class="col-12 col-md-6 col-lg-3 mb-4">
            <h4>Contact Us</h4>
            <ul class="pl-0 mt-4">
              <li>
                <i class="fas fa-map-marked-alt"></i>
                <p class="pl-2">Ekantakuna, Lalitpur 44600</p>
              </li>
              <hr />
              <li>
                <i class="fas fa-at"></i>
                <p class="pl-2">info@tisacafe.com</p>
              </li>
              <hr />
              <li>
                <i class="fas fa-phone-volume"></i>
                <p class="pl-2">Phone: 9846615891, 9847020440</p>
              </li>
              <hr />
            </ul>
          </div>

          <div class="col-12 col-md-6 col-lg-3 mb-4">
            <h4>Our Services</h4>
            <ul class="pl-0 mt-4">
              <li>
                <p>
                  <i class="fas fa-arrow-right"></i> Fine Dining & Concierge
                </p>
              </li>
              <li>
                <p>
                  <i class="fas fa-arrow-right"></i> Quick Counter Service
                </p>
              </li>
              <li>
                <p>
                  <i class="fas fa-arrow-right"></i> Family Style Service
                </p>
              </li>
              <li>
                <p>
                  <i class="fas fa-arrow-right"></i> Quick Delivery Service
                </p>
              </li>
              <li>
                <p>
                  <i class="fas fa-arrow-right"></i> Buffet Table Service
                </p>
              </li>
              <li>
                <p>
                  <i class="fas fa-arrow-right"></i> Traditional Counter Service
                </p>
              </li>
            </ul>
            <br />
          </div>

          <div class="col-12 col-md-6 col-lg-3 hours mb-4">
            <h4>Opening Hours</h4>
            <ul class="pl-0 mt-4">
              <li>
                <p>Sun - Fri</p>
                <p>10:00 am - 9:00 pm</p>
              </li>
              <hr />
              <li>
                <p>Saturday</p>
                <p>10:00 am - 9:00 pm</p>
              </li>
              <hr />
            </ul>
            <br />

            <h4>Bar Opening</h4>
            <ul class="pl-0 mt-4">
              <li>
                <p>Sun - Fri</p>
                <p>10:00 am - 9:00 pm</p>
              </li>
              <hr />
              <li>
                <p>Saturday</p>
                <p>10:00 am - 9:00 pm</p>
              </li>
              <hr />
            </ul>
          </div>

          <div class="col-12 col-md-6 col-lg-3">
            <div id="fb-container">
              <!-- <img
              src="http://seabreeze.themetechmount.net/wp-content/uploads/2019/07/footer-banner.png"
              class="img-fluid"
              />-->
              <div
                class="fb-page"
                data-href="https://www.facebook.com/TisaRestaurantEspresso/"
                data-tabs="timeline"
                data-height="336"
                data-small-header="false"
                data-adapt-container-width="true"
                data-hide-cover="false"
                data-show-facepile="true"
              >
                <blockquote
                  cite="https://www.facebook.com/TisaRestaurantEspresso/"
                  class="fb-xfbml-parse-ignore"
                >
                  <a
                    href="https://www.facebook.com/TisaRestaurantEspresso/"
                  >Tisa Restaurant &amp; Espresso</a>
                </blockquote>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row no-gutters text-center mt-2 copy pt-3 px-2">
        <div class="col-12">
          <p>Copyright &copy; {{new Date().getFullYear()}} Tisa Restaurant &amp; Espresso. Crafted by theGimmickBox</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
window.onresize = () => {
  window.FB.XFBML.parse();
};
</script>

<style scoped lang="scss">
#footer {
  background-image: url(~@/assets/footer-bg.jpg);
  color: #fff;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.wrapper {
  background-color: rgba(10, 20, 30, 0.93);
}

ul {
  list-style: none;
  li {
    display: flex;
    font-weight: 300;
    font-size: 15px;
    svg {
      color: #c5a572;
    }
  }

  hr {
    margin-top: 0 !important;
    margin-bottom: 16px !important;
    border-top: solid rgba(255, 255, 255, 0.15) 1px;
  }
}

.hours {
  li {
    justify-content: space-between;
  }
}

.copy {
  font-size: 13px;
  background-color: rgb(10, 20, 30);
}
</style>
