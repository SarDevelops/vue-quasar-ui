<template>
  <q-page class="row part">
    <Order></Order>
    <AddToCart></AddToCart>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
// import ExampleComponent from 'components/ExampleComponent.vue';
import { defineComponent, ref } from 'vue';
import AddToCart from 'src/components/AddToCart.vue';
import Order from 'src/components/order.vue';

export default defineComponent({
  name: 'OrderPage',
  components: { AddToCart, Order },
});
</script>
