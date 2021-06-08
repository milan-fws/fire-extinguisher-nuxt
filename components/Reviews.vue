<template>
  <div>
      <h3>Customer reviews</h3>
      <div v-if="!$fetchState.pending">
        <ReviewCard 
          v-for="review in reviewers.results" 
          :key="review.login.uuid"
          :review="review"
        />
      </div>
      <div v-else>
        Loading...
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            reviewers: []
        }
    },
    async fetch() {
        this.reviewers = await this.$axios.$get('https://randomuser.me/api/?results=5');
    }

}
</script>

<style>

</style>