<template>
  <q-layout view="hhh lpR fff">
    
    <Header @toggleLeftDrawer="toggleLeftDrawer" :leftDrawerOpen="leftDrawerOpen" />

    <q-drawer v-model="leftDrawerOpen" side="left" overlay bordered >
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer bordered class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <div class="text-weight-light text-subtitle1">Buy And Sell</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import { ref } from 'vue'
import Header from 'components/Header.vue'
export default {
  components: {
    Header
  },
  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer (value) {
        leftDrawerOpen.value = value
      }
    }
  }
}
</script>