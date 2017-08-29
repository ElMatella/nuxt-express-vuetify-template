{{{{raw}}}}
<template>
  <v-app light>
    <my-drawer/>
    <my-toolbar/>
    <main>

      <v-container fluid >
        <v-layout row justify-center>
          <img src="~assets/img/logo.png" alt="Nuxt.js Logo" class="logo" />
        </v-layout>
        <v-layout row>
          <v-flex xs4 offset-xs4>
            <v-card light>
              <v-card-title class="headline">{{ error.statusCode }}</v-card-title>
              <v-card-text>
                <v-alert error value="true">
                  {{ error.message }}
                </v-alert>
                <v-btn block flat nuxt to="/" v-if="error.statusCode === 404">Back to Homepage</v-btn>
              </v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>

    </main>
    <my-footer/>
  </v-app>
</template>
{{{{/raw}}}}

<script>
  import MyFooter from '~/components/Footer.vue'
  import MyDrawer from '~/components/Drawer.vue'
  import MyToolbar from '~/components/Toolbar.vue'

  export default {
    props: ['error'],
    components: {
      MyFooter,
      MyDrawer,
      MyToolbar
    }
  }
</script>

<style scoped>

</style>
