<template>
  <div>
    <b-row>
      <b-col>
        <h1>Ledger<small class="text-muted"> Jul 2021</small></h1>
      </b-col>
    </b-row>
    <b-row>
      <DxDataGrid
      >
      </DxDataGrid>
    </b-row>
  </div>
</template>

<script>
  import DxDataGrid from 'devextreme-vue/data-grid';

  export default {
    components: {
      DxDataGrid
    }
  }

</script>

<style scoped>

</style>