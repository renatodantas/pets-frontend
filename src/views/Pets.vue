<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12>
        <ListarPets :pets="pets"/>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import ListarPets from '../components/ListarPets'

export default {
  components: {
    ListarPets
  },
  data() {
    return {
      pets: []
    }
  },
  created() {
    fetch('http://localhost:8080/api/pets')
      .then(res => res.json())
      .then(json => this.pets = json)
      .then(() => console.log(this.pets))
  }
}
</script>
