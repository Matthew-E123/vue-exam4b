<script>
import Nav from './components/Nav.vue'
export default {
  components: {
    Nav
  },
  data() {
    return {
      plants: [
        {id: 1, name: "Sunflower", type: "Outdoor", instock: true},
        {id: 2, name: "Lavender", type: "Indoor", instock: true},
        {id: 3, name: "Sweet Potato Vines", type: "Outdoor", instock: false}
      ],
      filterType: "All"
    }
  },
  methods: {
    handleFilter(type){
      this.filterType = type;
      console.log(this.filterType)
    }
  }
}
</script>


<template>
  <Nav @filter-plants="handleFilter"></Nav>
  <h1>Plant Store App  </h1>
  <router-view :plants="plants" :filterType="filterType" />
</template>

