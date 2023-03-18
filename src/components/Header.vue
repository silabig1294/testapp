<template>
    <v-app-bar app color="transparent" dark>
      <v-toolbar-title>
        <router-link to="/" style="{background-color: #fff;color: #000;}">MyApp</router-link>
      </v-toolbar-title>
  
      <v-spacer></v-spacer>
  
      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-account-circle</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-if="loggedIn" @click="logout">
            <v-list-item-title>Logout</v-list-item-title>
          </v-list-item>
          <v-list-item v-else>
            <router-link to="/login">
              <v-list-item-title>Login</v-list-item-title>
            </router-link>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
  </template>
  
  <script>
  export default {
    props: {
      loggedIn: {
        type: Boolean,
        required: true
      },
      logout: {
        type: Function,
        required: true
      }
    }
  }
  </script>
  