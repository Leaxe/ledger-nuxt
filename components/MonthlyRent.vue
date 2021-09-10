<template>
  <b-jumbotron>
    <b-row>
      <b-col>
        <h1>Monthly Rent: $1000</h1>
      </b-col>
      <b-col cols="2" class="align-self-center">
        <b-button class="float-right">Button here</b-button>
      </b-col>
    </b-row>
    
    <b-table id="rent_table" :items="items" :fields="fields" :borderless=true></b-table>
  </b-jumbotron>
</template>

<script lang="ts">
import { BTable } from '../node_modules/bootstrap-vue/esm/components/table';
export default {
  data(): {fields: BTable['fields'], items: BTable['items']} {
    return {
      fields: [
        {
          key: 'rentType',
          label: '',
          headerTitle: 'Rent Type',
          isRowHeader: true,
          class: ['rent-type-column', 'text-right']

        },
        'a',
        'b',
        'c',
        'd'
      ],
      items: [
        { rentType: 'Base Rent', a: '$1', b: '$2', c: '$3', d: '$4' },
        { rentType: 'Balanced Rent',  a: '$1', b: '$2', c: '$3', d: '$4' },
      ],
    }
  },
}
</script>

<style lang="scss">
//should this be scoped? I had to disable to allow the following class to apply
.rent-type-column {
   width: 8.3em;
}
</style>