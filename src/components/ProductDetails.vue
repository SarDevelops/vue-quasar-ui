<template>
  <div class="q-pa-md">
    <div class="col">
      <q-carousel
        animated
        v-model="slide"
        infinite
        arrows
        transition-prev="slide-right"
        transition-next="slide-left"
        class="slider-images"
      >
        <q-carousel-slide
          :name="1"
          img-src="https://cdn.quasar.dev/img/mountains.jpg"
        />
        <q-carousel-slide
          :name="2"
          img-src="https://cdn.quasar.dev/img/parallax1.jpg"
        />
        <q-carousel-slide
          :name="3"
          img-src="https://cdn.quasar.dev/img/parallax2.jpg"
        />
        <q-carousel-slide
          :name="4"
          img-src="https://cdn.quasar.dev/img/quasar.jpg"
        />
      </q-carousel>
      <div class="slide-page q-pt-lg">
        <div class="text-h6">
          Price: <span class="text-xl text-bold q-pr-lg">$50</span>
          <span class="text-sm discount"> -80% </span>
        </div>
      </div>
      <div class="slide-page q-pt-xl">
        <div class="text-h6 q-pr-sm">Quantity:</div>
        <q-btn
          style="background-color: white; color: black"
          label="-"
          @click="decrement"
        />
        <div class="q-pl-sm q-pr-sm text-bold text-xl">{{ value }}</div>
        <q-btn
          style="background-color: white; color: black"
          label="+"
          @click="increment"
        />
      </div>

      <div class="slide-page slider-info" style=" min-height: auto;">
        <p>
          <span
            class=""
            style="font-weight: 500; font-size: 18px; line-height: 28px"
          >
            Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt.
            Pulvinar sed justo et viverra pellentesque.
          </span>
          <br />
          <br />
          <span
            style="font-weight: 500; font-size: 18px; "
          >
            Mauris augue nulla proin vel a. Facilisis fringilla molestie
            dignissim elit orci malesuada. Lorem sit sagittis vitae nulla id.
            Mauris ipsum sed sed faucibus. Nulla amet metus gravida orci
            faucibus nisl eros arcu lorem. Nullam ornare molestie nam id gravida
            volutpat bibendum sem feugiat. Neque vulputate in et maecenas porta
            mi tellus. In massa porttitor urna quis volutpat at.
          </span>
        </p>
      </div>
      <div class="row slide-page slider-info" style="min-height: auto;">
        <div class="q-pa-md q-gutter-sm">
          <q-card class="my-card rounded cards-list">
            <q-card-section class="justify">
              <q-icon name="lock" />
              Guaranteed <span class="text-bold">Safe</span> & <span class="text-bold">Secure</span> Checkout
            </q-card-section>
            <ul class="logo-list">
              <li>
                <img src="../assets/web-images/master.svg" />
              </li>
              <li>
                <img src="../assets/web-images/visa.svg" />
              </li>
              <li>
                <img src="../assets/web-images/paypal_icon.svg" />
              </li>
              <li style="background-color: #006fcf">
                <img src="../assets/web-images/amex.svg" />
              </li>
              <li>
                <img src="../assets/web-images/jcb.svg" />
              </li>
              <li>
                <img src="../assets/web-images/dinners_club.svg" />
              </li>
            </ul>
          </q-card>
        </div>
        <div class="q-pa-md q-gutter-sm">
          <q-card class="my-card rounded cards-list">

            <div class="row">
              <img src="../assets/web-images/support.svg" alt="" />
              <div class="col">
                <div class="text-h6">24/7</div>
                <div class="text-h5">Support</div>
              </div>
            </div>
          </q-card>
        </div>
      </div>

      <div class="slide-page slider-info row" style=" min-height: auto !important;">
        <q-btn
        class="done-btn"
        rounded
        label="Yes I want"
        icon-right="arrow_right_alt"
      />

    </div>
    <div class="slide-page slider-info row text-bold txt-sub-color" style="  min-height: auto !important;"> No, Thanks</div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  data() {
    return {
      value: 0,
    };
  },
  methods: {
    decrement() {
      if (this.value) {
        this.value -= 1;
      }
    },
    increment() {
      this.value += 1;
    },
  },
  setup() {
    return {
      slide: ref(1),
      autoplay: ref(true),
    };
  },
};
</script>
