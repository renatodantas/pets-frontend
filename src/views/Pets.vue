<template>
  <v-container>
    <div class="title">Listar Pets</div>

    <v-layout>
      <v-flex>
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
