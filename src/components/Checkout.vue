<template>
 <q-page-container class="col-sm-12 col-md-6">
    <div class="heading-txt">Checkout</div>
    <q-breadcrumbs separator=">" class="txt-sub-color" active-color="#84849A">
      <q-breadcrumbs-el class="txt-sub-color" label="Cart" />
      <q-breadcrumbs-el label="Shipping & Billing" class="txt-active-color" />
    </q-breadcrumbs>

    <q-card class="time-card">
      <q-card-section>
        <div class="text-h6">🔥 Your cart is reserved for 10:00 minutes</div>
        <div id="clock">
          <!-- <p class="date">{{ date }}</p>
          <p class="time">{{ time }}</p> -->
          <div id="time" class="flex justify-center"><span class="time_body"> 00 </span>  : <span class="time_body">{{ minutes }}</span>  : <span class="time_body"> {{ seconds }}</span> </div>
        </div>
      </q-card-section>
    </q-card>
    <q-card class="exp-checkout">
      <q-card-section>
        <div class="text-h6">Express Checkout</div>
        <div class="q-pa-md q-gutter-sm">
          <q-btn class="btn-shoppay btn-size">
            <img src="../assets/web-images/shoopay_text.png" alt=""
          /></q-btn>
          <q-btn class="btn-paypal btn-size">
            <img src="../assets/web-images/paypal_text.png" alt=""
          /></q-btn>
          <q-btn class="btn-gpay btn-size">
            <img src="../assets/web-images/gpay_text.png" alt=""
          /></q-btn>
        </div>
      </q-card-section>
    </q-card>
    <div class="q-pa-md q-gutter-sm">
      <div class="text-h6">Contact Information</div>
      <q-input
        outcolor="purple-12"
        rounded
        color="purple-12"
        standout
        bottom-slots
        v-model="text"
        label="mail"
      >
        <template v-slot:prepend>
          <q-icon name="mail" />
        </template>
      </q-input>
    </div>

    <div class="q-pa-md q-gutter-sm">
      <div class="text-h6">Shipping Address</div>

      <q-select
        rounded
        outlined
        bottom-slots
        v-model="opt"
        :options="options"
        label="Country"
        :dense="dense"
        :options-dense="denseOpts"

      >
        <template v-slot:prepend>
          <q-icon name="place" />
        </template>
      </q-select>
      <div class="row justify-between">
        <q-input rounded outlined v-model="first_name" label="First Name" lazy-rules
          :rules="[ val => val && val.length > 0 || 'Enter First Name']" >
          <template v-slot:prepend>
            <q-icon name="person" />
          </template>
        </q-input>

        <q-input rounded outlined v-model="last_name" label="Last Name" lazy-rules
          :rules="[ val => val && val.length > 0 || 'Enter last Name']" >
          <template v-slot:prepend> <q-icon name="person" /> </template
        ></q-input>
      </div>

      <q-input rounded outlined v-model="address" label="Address">
        <template v-slot:prepend>
          <q-icon name="home" />
        </template>
      </q-input>
      <div class="row justify-between">
        <q-input rounded outlined v-model="city" label="City" > </q-input>
        <q-input rounded outlined v-model="postal_code" label="Postal Code"> </q-input>
      </div>
    </div>

    <div class="q-pa-md q-gutter-sm">
      <div class="text-h6">Shipping method</div>
      <div class="q-pa-md">
        <div class="q-gutter-sm flex justify-between">
          <q-radio right-label v-model="shape" val="ellipse" label="Ellipse" />
          <div class="text-h6">$10</div>
        </div>
        <div class="q-gutter-sm flex justify-between">
          <q-radio right-label v-model="shape" val="polygon" label="Polygon" />
          <div class="text-h6">$20</div>
        </div>
      </div>
    </div>

    <div class="q-pa-md q-gutter-sm">
      <div class="text-h6 text-bold">Payment Method</div>
      <div class="text-subtitle1 txt-sub-color">
        All transaction are secured and encryted
      </div>
      <div class="q-pa-md q-gutter-sm">
        <q-input rounded outlined v-model="card_number" label="Card number">
          <template v-slot:prepend>
            <q-icon name="credit_card" />
          </template>
        </q-input>
        <q-input rounded outlined v-model="card_name" label="Name on card">
          <template v-slot:prepend>
            <q-icon name="person" />
          </template>
        </q-input>
        <div class="row justify-between">
          <q-input rounded outlined v-model="date" label="MM/YY"> </q-input>

          <q-input rounded outlined v-model="cvv" label="CVV"> </q-input>
        </div>
      </div>
      <div class="q-gutter-sm">
        <q-checkbox v-model="teal" color="teal">
          By checking this box, I acknowledge that I have read and agree to the
          <span class="text-bold">Terms of Service</span>, and
          <span class="text-bold"> Monthly Billing Terms </span> of this website
          and want to opt-in for the monthly billed Dream Collection
          Club®</q-checkbox
        >
      </div>
    </div>

    <div class="q-pa-md q-gutter-sm">
      <div class="text-h6 text-bold">Billing Address</div>
      <div class="text-subtitle1 txt-sub-color">
        Specify the address for your payment option
      </div>
      <div class="q-pa-md">
        <div class="q-gutter-sm">
          <q-radio
            right-label
            v-model="shape"
            val="ellipse"
            label="Same as shipping address"
          />
        </div>
        <div class="q-gutter-sm">
          <q-radio
            right-label
            v-model="shape"
            val="polygon"
            label="Use a different billing address"
          />
        </div>
      </div>
      <q-btn
        class="done-btn"
        rounded
        label="Complete Order"
        icon-right="arrow_right_alt"
        type="submit"
        @submit.prevent.stop="onSubmit"

      />
    </div>
  </q-page-container>
</template>

<script>
import { ref } from 'vue';
export default {
  el: '#clock',
  data() {
    return {
      intervalId: 0,
      minutes: '05',
      seconds: '00',
      first_name:null
    }
  },
  mounted () {
    this.startTimer(60 * 10)
  },
  beforeDestroy () {
    clearInterval(this.intervalId)
  },
  methods: {
    startTimer (duration, display) {
      var timer = duration,
        minutes,
        seconds
      this.intervalId = setInterval(() => {
        this.minutes = parseInt(timer / 60, 10)
        this.seconds = parseInt(timer % 60, 10)

        this.minutes = this.minutes < 10 ? "0" + this.minutes : this.minutes
        this.seconds = this.seconds < 10 ? "0" + this.seconds : this.seconds

        if (--timer < 0) {
          timer = duration
        }
      }, 1000)
    },
    onSubmit () {
      this.$refs.first_name.validate()


      if (this.$refs.name.hasError ) {
        this.formHasError = true
      }
      else {
        this.$q.notify({
          icon: 'done',
          color: 'positive',
          message: 'Submitted'
        })
      }
    },
  },

  setup() {
    return {
      opt: ref(null),

      options: ['UAS', 'UK', 'CANADA', 'INDIA', 'IRAN'],
      text: ref(''),
      first_name: ref(''),
      last_name: ref(''),
      address: ref(''),
      city: ref(''),
      postal_code: ref(''),
      cvv: ref(''),
      card_number: ref(''),
      date: ref(''),
      card_name: ref(''),
      ph: ref(''),

      dense: ref(false),
      teal: ref(true),
      denseOpts: ref(false),
      shape: ref('line'),
    };
  }
}
</script>

<style>

</style>
