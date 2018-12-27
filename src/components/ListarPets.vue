<template>
  <v-flex>
    <v-data-table 
      :headers="headers"
      :items="pets"
      class="elevation-2">

        <template slot="items" slot-scope="{ item }">
          <td>{{ item.nome }}</td>
          <td>{{ item.tipo.descricao }}</td>
          <td>{{ item.dono.nome }}</td>
        </template>

        <template slot="pageText" slot-scope="props">
          Linha {{ props.pageStart }} - {{ props.pageStop }} de {{ props.itemsLength }}
        </template>

        <template slot="no-data">
          Nenhum registro encontrado
        </template>

    </v-data-table>
  </v-flex>
</template>

<script>
export default {
  name: 'ListarPets',
  props: {
    pets: {
      type: Array,
      required: true
    }
  },
  data: () => ({
    headers: [
      { text: 'Nome', align: 'left', value: 'nome' },
      { text: 'Tipo', align: 'left', value: 'tipo.descricao' },
      { text: 'Dono', align: 'left', value: 'dono.nome' },
    ]
  })
}
</script>
