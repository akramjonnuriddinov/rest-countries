<template>
  <!-- SITE-HEADER -->
  <header class="site-header">
    <div class="container site-header__container">
      <a class="site-header__logo" href="#">Where in the world?</a>
      <button @click="darkMode()" class="dark-mode-btn">
        <svg width="18" height="17" viewBox="0 0 18 17" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M12.5532 11.815C8.66857 11.815 5.51929 8.92783 5.51929 5.36821C5.51929 4.0253 5.96679 2.78158 6.73143 1.75C3.69036 2.69515 1.5 5.33122 1.5 8.43807C1.5 12.3385 4.94929 15.5 9.20357 15.5C12.5929 15.5 15.4696 13.4932 16.5 10.7045C15.375 11.4048 14.0161 11.815 12.5532 11.815Z" fill="currentColor" stroke="#111517" stroke-width="1.25"/>
        </svg>
        <span class="dark-mode-btn__text">Dark Mode</span>
      </button>
    </div>
  </header>
  <!-- /SITE-HEADER -->

</template>

<script>
export default {
  name: 'Header',
  data() {
    return {

    }
  },
  methods: {
    darkMode() {
      document.body.classList.toggle('dark-mode');
    }
  }
}
</script>

<style scoped>

.site-header {
  box-shadow: 0px 2px 4px 0px var(--shadow-light);
  background-color: var(--card-bg-light);
}

.site-header__container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 23px;
  padding-bottom: 23px;
}

.site-header__logo {
  text-decoration: none;
  color: var(--text-light);
  font-size: 24px;
  line-height: 32.74px;
  font-weight: 800;
  margin-right: 20px;
}

.dark-mode-btn {
  background-color: transparent;
  border: none;
  outline: none;
  display: flex;
  align-items: center;
  color: var(--text-light);
  font-size: 16px;
  line-height: 21.82px;
  font-weight: 600;
  cursor: pointer;
}

.dark-mode-btn__text {
  margin-left: 8px;
}
</style>