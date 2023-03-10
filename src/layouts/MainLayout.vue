<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <div class="container">
        <q-toolbar>
          <q-toolbar-title>
            <img src="../assets/logo/Logo.svg" />
          </q-toolbar-title>
        </q-toolbar>
      </div>
    </q-header>
    <q-page-container class="container">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'MainLayout',
  components: {},
  setup() {
    return {};
  },
});
</script>
