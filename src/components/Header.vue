<template>
  <q-header>
    <div class="row no-wrap">
      <q-toolbar class="col-4">
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          <span class="gt-sm">
            Buy And Sell
          </span>
        </q-toolbar-title>
      </q-toolbar>
      <q-toolbar class="col-4">
        <q-input v-model="searchText" bg-color="white" standout="bg-white text-secondary" rounded outlined dense class="q-my-sm search-input">
          <template v-slot:append>
            <q-icon name="search" @click="text = ''" class="cursor-pointer" />
          </template>
        </q-input>
      </q-toolbar>
      <q-toolbar class="col-4">
      </q-toolbar>
    </div>
  </q-header>
</template>

<style scoped>
.search-input {
  width: 100%;
  color: #fff
}
</style>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Header',
  props: [
    'leftDrawerOpen'
  ],
  data: function () {
    return {
      searchText: ''
    }
  },
  methods: {
    toggleLeftDrawer (event) {
      this.$emit('toggleLeftDrawer', !this.leftDrawerOpen)
    }
  }
})
</script>
