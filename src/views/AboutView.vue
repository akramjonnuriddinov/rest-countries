<template>
  <div class="about">
    <!-- <h1>This is an about page</h1> -->
    <div class="container">
      <h1 v-if="country">{{country.name}}</h1>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  props: ['alphaCode'],
  data() {
    return {
      country: null
    }
  },
  mounted() {
    this.fetchCountry()
  },
  methods: {
   async fetchCountry() {
      const res = await axios.get('https://restcountries.com/v2/alpha/' + this.alphaCode)
      this.country = res.data
    }
  }
}
</script>
