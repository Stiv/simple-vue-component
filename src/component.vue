<template>
  <div>
    <ag-grid-vue style="width: 500px; height: 500px;"
                 class="ag-theme-balham"
                 :gridOptions="gridOptions"
                 :columnDefs="columnDefs"
                 :rowData="rowData">
    </ag-grid-vue>
  </div>
</template>

<script>
import "../node_modules/ag-grid/dist/styles/ag-grid.css";
import "../node_modules/ag-grid/dist/styles/ag-theme-balham.css";

export default {
  name: 'SimpleComponent',
    data() {
        return {
            gridOptions: {},
            columnDefs: null,
            rowData: null
        }
    },
    components: {
        'ag-grid-vue': AgGridVue
    },
    beforeMount() {
        this.columnDefs = [
            {headerName: 'Make', field: 'make'},
            {headerName: 'Model', field: 'model'},
            {headerName: 'Price', field: 'price'}
        ];

        this.rowData = [
            {make: 'Toyota', model: 'Celica', price: 35000},
            {make: 'Ford', model: 'Mondeo', price: 32000},
            {make: 'Porsche', model: 'Boxter', price: 72000}
        ];
    }
}
</script>

<style scoped>

</style>
