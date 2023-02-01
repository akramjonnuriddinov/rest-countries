<template>
  <Header />
  <router-view></router-view>
</template>

<script>
import Header from './components/Header.vue';

export default {
  components: {
    Header
  }
}
</script>

<style>

:root {
  --text-light: #111517;
  --card-bg-light: #FFFFFF;
  --shadow-light: #0000000E;
  --main-bg-light: #FAFAFA;
  --placeholder-light: #848484;
}

.dark-mode {
  --text-light: #ffffff;
  --card-bg-light: #2B3844;
  --shadow-light: #00000008;
  --main-bg-light: #202C36;
  --placeholder-light: #ffffff;
}

html {
  height: 100%;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}

body {
  display: flex;
  flex-direction: column;
  margin: 0;
  padding: 0;
  font-size: 14px;
  line-height: 16px;
  font-weight: 400;
  font-family: 'Nunito Sans', sans-serif;
  background-color: var(--main-bg-light);
}

.container {
  max-width: 1320px;
  width: 100%;
  padding-left: 20px;
  padding-right: 20px;
  margin-left: auto;
  margin-right: auto;
}
</style>