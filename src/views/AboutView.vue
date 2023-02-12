<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h1 v-if="country">{{country.name}}</h1>
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
    console.log(this.alphaCode)
      const res = await axios.get('https://restcountries.com/v2/alpha/' + this.alphaCode)
      this.country = res.data
    }
  }
}
</script>
