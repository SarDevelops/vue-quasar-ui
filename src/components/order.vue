<template>
  <div class="col-sm-12 col-md-6">
    <div class="slider-images slide-page" style="min-height: auto">
      <img src="../assets/web-images/like.svg" alt="" />
    </div>
    <div class="slide-page">
      <span class="text-bold" style="font-size: 24px"
        >Thank you for your order</span
      >
    </div>

    <span class="txt-sub-color slide-page" style="font-size: 16px"
      >Your order is confirmed</span
    >
    <div class="slide-page q-pt-sm q-pb-sm">
      <span class="label lable-tages rounded slide-pag">Order ID: #10040 </span>
    </div>
    <div class="slide-page">
      <q-btn
        class="done-btn"
        rounded
        label="Back to Shop"
        icon="keyboard_backspace"
      />
    </div>
    <div class="q-pa-md q-gutter-sm">
      <q-card class="my-card rounded cards-list">
        <ul class="list_points">
          <div class="row">
            <li>
              <div class="txt-sub-color">Name:</div>
              <span class="text-h6" style="font-size: 14px">Oleo Bone</span>
              <div class="txt-sub-color">Shipping Address:</div>
              <span class="text-h6" style="font-size: 14px"
                >4140 Parker Rd. Allentown, New Mexico 31134</span
              >
              <div class="txt-sub-color">Shipping:</div>
              <span class="text-h6" style="font-size: 14px">Free</span>
            </li>
            <li>
              <div class="txt-sub-color">Email:</div>
              <span class="text-h6" style="font-size: 14px"
                >oleo_bone@gmail.com</span
              >
              <div class="txt-sub-color">Billing Address:</div>
              <span class="text-h6" style="font-size: 14px"
                >Same as shipping</span
              >
              <div class="txt-sub-color">Payment Method:</div>
              <span class="text-h6" style="font-size: 14px">Credit Card</span>
            </li>
          </div>
        </ul>
      </q-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TestTaskOrder',

  data() {
    return {};
  },

  methods: {},
};
</script>

<style lang="scss" scoped></style>
