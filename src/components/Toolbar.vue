<template>
  <v-toolbar app>
      
    <v-toolbar-title class="headline custom-toolbar">
      <router-link to="/">
        <v-img class="logo" :src="require('../assets/logo.png')" height="32" width="32" />
        <span>PETS</span>
      </router-link>
    </v-toolbar-title>
    
    <v-spacer></v-spacer>
    
    <v-toolbar-items>
      <v-btn flat to="/pets">
        Pets
      </v-btn>
      <v-btn flat to="/donos">
        Donos
      </v-btn>
      <v-btn flat to="/about">
        About
      </v-btn>
    </v-toolbar-items>

  </v-toolbar>
</template>

<style scoped>
  .custom-toolbar > a {
    text-decoration: none;
    font-weight: bold;
    color: #009688;
  }
  .logo {
    float: left;
    margin-right: 5px
  }
</style>
