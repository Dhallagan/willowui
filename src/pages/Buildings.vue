<template>
<page>
  

  <page-header
    title="Buildings"
  >
  <template slot="action-right">
    <willow-button primary>Add Building</willow-button>
  </template>

  </page-header>

  <b-card class="w-100">
  <willow-button v-b-toggle.collapse1 outline>Filters +</willow-button>

  <b-collapse id="collapse1" class="mt-2">
    <b-card>
      <p class="card-text">Advanced Options:</p>
 <!--
        <b-col cols="6">
        <b-form-group id="fieldsetHorizontal"
                      description="Less Than"
                      label="Price"
                      label-for="inputHorizontal">
            <b-select :options="[{ value: null, text: '$1000' },{ value: 'a', text: '$2000' }]"></b-select>
          </b-form-group>
          
        </b-col>
        <b-col cols="6">
          <b-form-group id="fieldsetHorizontal"
                      description="Number of Bedrooms"
                      label="Beds"
                      label-for="inputHorizontal">
            <b-select :options="[{ value: null, text: '1' },{ value: 'a', text: '2' }]"></b-select>
          </b-form-group>
        </b-col>
      </b-row>
      -->
      <b-row>
        <b-col cols="6">
          <b-form-group id="fieldsetHorizontal"
                      description="City"
                      label="City"
                      label-for="inputHorizontal">
            <b-select :options="[{ value: null, text: 'Newark' },{ value: 'a', text: 'Lyons' }]"></b-select>
          </b-form-group>
        </b-col>
        <b-col cols="6">
        <b-form-group id="fieldsetHorizontal"
                      description="Condo, Duplex, Single Family, etc."
                      label="Type"
                      label-for="inputHorizontal">
            <b-select :options="[{ value: null, text: 'Duplex' },{ value: 'a', text: 'Condo' }]"></b-select>
          </b-form-group>
          
        </b-col>
        <b-col cols="6">
          <b-form-group id="fieldsetHorizontal"
                      description="Property Owner"
                      label="Owner"
                      label-for="inputHorizontal">
            <b-select :options="[{ value: null, text: 'Apollo Residential' },{ value: 'a', text: 'Scott Wagner' }]"></b-select>
          </b-form-group>
        </b-col>

      </b-row>
    </b-card>
  </b-collapse>
  <br><br>

    <b-form-input 
      placeholder="Search..."
    ></b-form-input>

  <br>

  <b-table hover :items="buildings" :fields="fields"
    @row-clicked="goTo"
  >
  </b-table>

  </b-card>


</page>
</template>

<script>
export default {
  mounted() {
    this.buildings = this.$store.getters.getBuildings;
  },

  data() {
    return {
      fields: ["property", "location", "owner", "type"],
      buildings: null
    };
  },

  methods: {
    goTo(building, index) {
      console.log(building);
      this.$router.push({ path: "/Buildings/" + building.id });
    }
  }
};
</script>

<style>

</style>
