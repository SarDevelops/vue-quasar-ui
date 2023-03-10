<template>
  <div class="col-sm-12 col-md-6">
    <q-card-section>
      <div class="q-pa-md q-gutter-sm">
        <div style="display: flex">
          <div class="flex" style="width: 100%">
            <q-img
              src="https://picsum.photos/500/300"
              loading="lazy"
              spinner-color="white"
              height="70px"
              width="65px"
              style="border-radius: 8px"
              class="relative-position"
            >
              <!-- <span class="circular label bg-primary text-white">2</span> -->
            </q-img>
            <div class="text-h6" style="margin-left: 10px">Nike sneakers</div>
          </div>
          <div class="text-h6">$120.90</div>
        </div>
      </div>
      <div class="q-pa-md q-gutter-sm">
        <div style="display: flex">
          <div class="flex" style="width: 100%">
            <q-img
              src="https://picsum.photos/500/300"
              loading="lazy"
              spinner-color="white"
              height="70px"
              width="65px"
              style="border-radius: 8px"
            >
              <q-badge class="notificaion-icon" text-color="white" floating
                >2</q-badge
              >
            </q-img>
            <div class="text-h6" style="margin-left: 10px">Nike sneakers</div>
          </div>
          <div class="text-h6">$120.90</div>
        </div>
      </div>
      <div class="q-pa-md q-gutter-sm">
        <div style="display: flex">
          <div class="flex" style="width: 100%">
            <q-img
              src="https://picsum.photos/500/300"
              loading="lazy"
              spinner-color="white"
              height="70px"
              width="65px"
              style="border-radius: 8px"
            >
              <q-badge class="notificaion-icon" text-color="white" floating
                >2</q-badge
              >
            </q-img>
            <div class="text-h6" style="margin-left: 10px">Nike sneakers</div>
          </div>
          <div class="text-h6">$120.90</div>
        </div>
      </div>
      <hr />
      <div class="q-pa-md q-gutter-sm">
        <div class="flex justify-between" style="width: 100%">
          <div class="text-h6">Subtotal:</div>
          <div class="text-h6" style="margin-left: 10px">$362.70</div>
        </div>
        <div class="flex justify-between" style="width: 100%">
          <div class="text-h6">Shipping:</div>
          <div class="text-h6" style="margin-left: 10px">Free</div>
        </div>
      </div>
      <hr />
      <div class="q-pa-md q-gutter-sm">
        <div class="flex justify-between" style="width: 100%">
          <div class="text-h6">Totle</div>
          <div class="text-h6" style="margin-left: 10px">$362.70</div>
        </div>
      </div>

      <div class="q-pa-md q-gutter-sm">
        <q-card class="my-card rounded cards-list">
          <q-card-section class="justify">
            <q-icon name="lock" />
            Lorem ipsum dolor sit amet, consectetur adipiscing elit
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
          <div class="text-h6">The ultimate jewellery club</div>
          <p class="text-h6 txt-sub-color">
            Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt.
            Pulvinar sed justo et viverra pellentesque.
          </p>
          <ul class="list_points">
            <li><q-icon name="check" /> Extra 10$ off!</li>
            <li><q-icon name="check" /> Free shipping on marked club items!</li>
            <li><q-icon name="check" /> Free returns on marked club items!</li>
          </ul>
        </q-card>
      </div>
    </q-card-section>
  </div>
</template>

<script>
export default {
  name: 'TestTaskAddToCart',
  data() {
    return {};
  },

  methods: {},
};
</script>
