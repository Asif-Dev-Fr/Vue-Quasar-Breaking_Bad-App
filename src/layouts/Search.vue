<template>
  <q-layout view="hHh Lpr fFf"> <!-- Be sure to play with the Layout demo on docs -->

    <!-- (Optional) The Header -->
    <q-header elevated class="row">
      <q-toolbar class="col-lg-7 col-12">
        <q-toolbar-title>
          Breaking Bad API
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs class="col-lg-5 col-12">
        <q-route-tab
          :to="{name: 'profile', params: { id:1 } }"
          replace
          label="Walter White"
        />
        <q-route-tab
          :to="{name: 'profile', params: { id:2 } }"
          replace
          label="Jessie Pinkman"
        />
        <q-route-tab
          :to="{name: 'profile', params: { id:'random' } }"
          replace
          label="Random"
        />
      </q-tabs>
    </q-header>

    <q-page-container>
      <!-- This is where pages get injected The key is added so it loads the changes -->
      <router-view  :key="$route.params.id" />
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  // name: 'LayoutName',

  data () {
    return {
      leftDrawer: true
    }
  }
}
</script>
