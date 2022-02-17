<template>
    <b-table striped hover 
        :items="items" 
        :fields="fields" 
        responsive="sm"       
        :sort-by.sync="sortBy"
        :sort-desc.sync="sortDesc"
        sort-icon-right
      >
          <template #cell(show_details)="row">
        <b-button size="sm" @click="row.toggleDetails" class="mr-2">
          {{ row.detailsShowing ? '' : 'Show'}} Details
        </b-button>

        <b-form-checkbox v-model="row.detailsShowing" @change="row.toggleDetails">
          Details via check
        </b-form-checkbox>
      </template>

      <template #row-details="row">
        <b-card>
          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Age:</b></b-col>
            <b-col>{{ row.item.age }}</b-col>
          </b-row>

          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Role:</b></b-col>
            <b-col>{{ row.item.role }}</b-col>
          </b-row>

          <b-button size="sm" @click="row.toggleDetails">Hide Details</b-button>
        </b-card>
      </template>
        </b-table>
</template>

<script>
var data = require('../external/getData');
export default {
  mounted() {
    this.items =  data.getDataTableau1();
  },
  data() {
      return {
        sortBy: 'last_name',
        sortDesc: false,
        fields: [
          { key: 'last_name', sortable: false },
          { key: 'first_name', sortable: true },
          { key: 'age', sortable: true },
          { key: 'show_details', sortable: false }
        ],
        items: []
      }
    }
  }
</script>
<style scoped>
table#table-transition-example .flip-list-move {
  transition: transform 1s;
}
</style>