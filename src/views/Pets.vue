<template>
  <v-container>
    <v-layout row wrap>
      <v-flex xs12>
        <v-toolbar class="elevation-1 primary white--text">
          <v-toolbar-title>Lista de Pets</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items>
            <v-btn flat class="white--text" @click.stop="exibirModalPet = true">
              <v-icon left>add_box</v-icon> Novo
            </v-btn>
          </v-toolbar-items>
        </v-toolbar>
        
        <ListarPets 
          :pets="pets"/>
        
        <EditarPet 
          :pet="petSelecionado" 
          :exibir="exibirModalPet" 
          @hide="exibirModalPet = false"/>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import ListarPets from '../components/ListarPets'
import EditarPet from '../components/EditarPet'

export default {
  components: {
    ListarPets,
    EditarPet
  },
  data() {
    return {
      pets: [],
      petSelecionado: {},
      exibirModalPet: false
    }
  },
  created() {
    fetch('http://localhost:8080/api/pets')
      .then(res => res.json())
      .then(json => this.pets = json)
      //.then(() => console.log(this.pets))
  }
}
</script>
