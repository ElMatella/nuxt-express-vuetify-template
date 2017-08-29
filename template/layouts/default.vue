<template>
  <v-app light>
    <my-drawer/>
    <my-toolbar/>
    <main>
      <nuxt/>
    </main>
    <my-footer/>
  </v-app>
</template>

<script>
  import MyFooter from '~/components/Footer.vue'
  import MyDrawer from '~/components/Drawer.vue'
  import MyToolbar from '~/components/Toolbar.vue'

  export default {
    components: {
      MyFooter,
      MyDrawer,
      MyToolbar
    }
  }
</script>

<style>

</style>
