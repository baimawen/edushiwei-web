<template>
  <q-layout class="bg-grey-1">

    <q-header elevated class="text-white" style="background: #24292e">
      <Header />
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal bordered class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg">
          </q-avatar>
          Title
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import Header from '../components/Header'
export default {
  data () {
    return {

    }
  },
  components: {
    Header
  }
}
</script>
