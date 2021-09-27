<template>
  <b-jumbotron class="jumbo">
    <b-row class="flex-nowrap">
      <b-col>
        <h2 class="header text-nowrap">
          Monthly Rent: 
          <span>$1000</span>
        </h2>
      </b-col>
      <b-col cols="2" class="align-self-center">
        <b-button variant="primary" class="float-right text-nowrap">Pay rent</b-button>
      </b-col>
    </b-row>
    
    <b-table id="rent_table" :items="items" :fields="fields" :borderless=true />
  </b-jumbotron>
</template>

<script lang="ts">
// import { BTable } from '../node_modules/bootstrap-vue/esm/components/table';
export default {
  // fields: BTable['fields'], items: BTable['items']
  data(): {} {
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

<style lang="scss" scoped>
::v-deep .rent-type-column {
  width: 8.3em;
}
</style>