{{{{raw}}}}
<template>
  <v-container fluid >
    <v-layout row justify-center>
      <img src="~assets/img/logo.png" alt="Nuxt.js Logo" class="logo" />
    </v-layout>
    <v-layout row>
      <v-flex xs4 offset-xs4>
        <v-card light>
          <v-card-title class="headline">Users</v-card-title>
          <v-card-text>
            <!-- TODO: v-list -->
            <ul class="users">
              <li v-for="(user, index) in users" :key="index" class="user">
                <nuxt-link :to="{ name: 'id', params: { id: index }}">
                  {{ user.name }}
                </nuxt-link>
              </li>
            </ul>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
{{{{/raw}}}}

<script>
  import axios from '~/plugins/axios'

  export default {
    async asyncData () {
      let { data } = await axios.get('/api/users')
      return {
        users: data,
        sidebar: false
      }
    },
    head () {
      return {
        title: 'Users'
      }
    }
  }
</script>

<style scoped>

</style>
