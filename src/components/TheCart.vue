<template>
  <div class="cart">
    <img class="cart__img" src="https://picsum.photos/267/160" alt="" width="267" height="160">
    <div class="cart__info">
      <h3 class="cart__title">lorem</h3>
      <p class="cart__text">
        <span class="cart__bold">Population: </span>
        <span class="cart__small">81,770,900</span>
      </p>
      <p class="cart__text">
        <span class="cart__bold">Region: </span>
        <span class="cart__small">Europe</span>
      </p>
      <p class="cart__text">
        <span class="cart__bold">Capital Berlin: </span>
        <span class="cart__small">81,770,900</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      KEY: `https://restcountries.com/v2/`,
    }
  },
  mounted() {
    this.setData();
  },
  methods: {
    async getData(alfa) {
      const result = await fetch(this.KEY + alfa);
      return result.json()
    },
    setData() {
      this.getData('alpha/uz').then((e) => console.log(e))
    }
  }
}
</script>

<style scoped>
.cart {
  max-width: 267px;
  width: 100%;
  background-color: var(--card-bg-light);
  box-shadow: 0px 0px 7px 2px var(--shadow-light);
  color: var(--text-light);
  margin-bottom: 75px;
  margin-right: 25px;
  border-radius: 5px;
  height: 336px;
}

.cart__img {
  border-radius: 5px;
}

.cart__info {
  padding: 24px 24px 46px;
}

.cart__title {
  margin-top: 0;
  margin-bottom: 16px;
  font-size: 18px;
  line-height: 26px;
  font-weight: 800;
  white-space: nowrap;
}

.cart__text {
  margin-top: 0;
  line-height: 16px;
  font-size: 14px;
  white-space: nowrap;
}

.cart__text:not(:last-child) {
  margin-bottom: 8px;
}

.cart__bold {
  font-weight: 600;
}

.cart__small {
  font-weight: 300;
}
</style>