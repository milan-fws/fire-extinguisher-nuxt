<template>
  <div class="container">
    <div v-if="rentals.length > 0">
      <MyItem
        v-if="rentals.length > 0"
        v-for="item in rentals"
        :key="item.id"
        :item="item"
      />
    </div>
    <div v-else>
      <h3>No ordered items</h3> 
    </div>
  </div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  data() {
    return {
      rentals: this.$store.state.myRentals
    }
  },
  layout: 'no-nav',
  

}
</script>

<style scoped>

</style>
