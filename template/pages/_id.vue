{{{{raw}}}}
<template>
  <v-container fluid >

    <v-layout row justify-center>
      <img src="~assets/img/logo.png" alt="Nuxt.js Logo" class="logo" />
    </v-layout>

    <v-layout row>
      <v-flex xs4 offset-xs4>
        <v-card-title class="headline">User</v-card-title>
        <v-card-text>
          <v-alert success value="true">
            {{ user.name }}
          </v-alert>
          <v-btn block flat nuxt to="/">Back to users</v-btn>
        </v-card-text>
      </v-flex>
    </v-layout>

  </v-container>
</template>
{{{{/raw}}}}

<script>
  import axios from '~/plugins/axios'

  export default {
    name: 'id',
    asyncData ({params, error}) {
      return axios.get('/api/users/' + params.id)
        .then((res) => {
          return {user: res.data}
        })
        .catch((e) => {
          error({statusCode: 404, message: 'User not found'})
        })
    },
    head () {
      return {
        title: `User: ${this.user.name}`
      }
    }
  }
</script>

<style scoped>

</style>
