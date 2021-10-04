<template>
  <q-layout view="hhh lpR fff">

    

    <q-header>
      <div class="row no-wrap">
        <q-toolbar class="col-4">
          <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
          <q-toolbar-title>
            <q-avatar>
              <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
            </q-avatar>
            Buy And Sell
          </q-toolbar-title>
        </q-toolbar>
        <q-toolbar class="col-4">
          <q-input color="secondary" standout="bg-white text-secondary" rounded outlined dense class="q-my-sm search-input">
            <template v-slot:append>
              <q-icon name="search" @click="text = ''" class="cursor-pointer" />
            </template>
          </q-input>
        </q-toolbar>
        <q-toolbar class="col-4">
        </q-toolbar>
        
      </div>
      
    
    </q-header>

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

<style scoped>

.search-input {
  width: 100%;
  color: #fff
}


</style>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
}
</script>