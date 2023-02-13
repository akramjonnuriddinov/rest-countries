<template>
  <main class="main-content">
    <section class="countries">
      <div class="countries__container container">
        <form class="search">
          <input class="search__input" type="text" placeholder="Search for a country…">
          <span class="search__icon">
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
            <g id="search">
            <path id="icon-search-black" fill-rule="evenodd" clip-rule="evenodd" d="M12.5 11H11.7L11.4 10.7C12.4 9.6 13 8.1 13 6.5C13 2.9 10.1 0 6.5 0C2.9 0 0 2.9 0 6.5C0 10.1 2.9 13 6.5 13C8.1 13 9.6 12.4 10.7 11.4L11 11.7V12.5L16 17.5L17.5 16L12.5 11ZM6.5 11C4 11 2 9 2 6.5C2 4 4 2 6.5 2C9 2 11 4 11 6.5C11 9 9 11 6.5 11Z" fill="currentColor"/>
            </g>
            </svg>
          </span>
        </form>
        <div class="countries__filter">
          
        </div>
      </div>
      <div class="container cart-container">
        <div class="countries__list">
          <router-link :to="{
            name: 'about', 
            params: {
              alphaCode: country.alpha2Code
            }}" 
            v-for="country in countries" 
            :key="country.alpha2Code" >
            <Card :country="country" />
          </router-link>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import Card from '../components/Card.vue';
import axios from 'axios'

export default {
  name: 'HomeView',
  components: {
    Card
  },
  data() {
    return {
      countries: []
    }
  },
  mounted() {
    this.setCountries()
  },
  methods: {
    async setCountries() {
      const res = await axios.get('https://restcountries.com/v2/all')
      this.countries = res.data
    }
  }
}
</script>

<style scoped>
.countries {
  padding-top: 48px;
}

.countries__container {
  margin-bottom: 46px;
}

.search {
  position: relative;
  max-width: 480px;
  width: 100%;
}

.search__input {
  width: 100%;
  border: none;
  outline: none;
  box-shadow: 0px 2px 9px 0px var(--shadow-light);
  padding: 19px 19px 19px 74px;
  background-color: var(--card-bg-light);
  color: var(--text-light);
  border-radius: 5px;
  font-size: 14px;
  line-height: 20px;
}

.search__input::placeholder {
  color: var(--placeholder-light);
}

.search__icon {
  position: absolute;
  top: 19px;
  left: 32px;
  color: var(--text-light);
}

.countries__list {
  margin-bottom: -75px;
  margin-right: -25px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
</style>