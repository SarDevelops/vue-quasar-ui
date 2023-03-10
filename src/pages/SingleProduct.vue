<template>
  <productDetails />
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
// import ExampleComponent from 'components/ExampleComponent.vue';
import { defineComponent } from 'vue';
import productDetails from 'src/components/ProductDetails.vue';

export default defineComponent({
  name: 'IndexPage',
  components: {
    productDetails,
  },
  setup() {
    return {};
  },
});
</script>
