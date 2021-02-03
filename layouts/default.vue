<template>
  <div class="layoutWrapper">
    <the-main-menu class="menu" />
    <nuxt class="content" />
    <footer class="main-footer">
      © Dominik Ilnicki
      {{ currentYear }}
    </footer>
  </div>
</template>
<script>
import TheMainMenu from '@/components/TheMainMenu'
export default {
  components: { TheMainMenu },
  computed: {
    currentYear() {
      const date = new Date()
      return date.getFullYear()
    }
  }
}
</script>
<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::after,
*::before {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: 'Quicksand', sans-serif;
  overflow-x: hidden;
}
ul {
  list-style: none;
}

a {
  text-decoration: none;
  color: #000;
}
.visuallyhidden {
  border: 0;
  clip: rect(0 0 0 0);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
  white-space: nowrap; /* 1 */
}
.layoutWrapper {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto auto auto;
  overflow-x: hidden;
  padding: 2vh 7vw;
  .menu {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 1;
  }
  .content {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 2;
    grid-row-end: 2;
  }
  .main-footer {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 3;
    grid-row-end: 3;
    font-weight: 800;
    display: flex;
    align-items: center;
    padding: 50px 0;
    span {
      font-weight: 100;
      opacity: 0.4;
    }
  }
}
.button {
  border-radius: 4px;
  text-align: center;
  position: relative;
  padding: 14px 20px;
  display: block;
  display: flex;
  justify-content: center;
  align-items: center;
  &::after {
    content: '';
    position: absolute;
    top: -15%;
    left: 6%;
    width: 100%;
    height: 100%;
    z-index: -9999;
    border-radius: inherit;
    transition: all 0.2s ease-in-out;
  }

  &:hover {
    &::after {
      transform: translate(-6%, 15%);
      border-color: transparent;
    }
  }
}
.button__icon {
  margin-right: 10px;
}
.button--primary {
  color: #fff;
  background: #000;

  &::after {
    background: #000;
  }
}

.button--ghost {
  color: #000;
  background: transparent;
  border: 0.11vw solid #000;

  &::after {
    content: '';
    background: transparent;
    border: inherit;
  }
}

.default-enter,
.default-leave-to {
  opacity: 0;
  transform: translateY(25px);
}
.default-enter-active {
  transition: transform 0.15s ease-out, opacity 0.2s ease-out;
}
.default-leave,
.default-enter-to {
  opacity: 1;
  transform: translateY(0);
}
.default-leave-active {
  transition: transform 0.15s ease-in, opacity 0.2s ease-in;
}

@media screen and (max-width: 720px) {
  .layoutWrapper {
    padding: 30px 20px;
  }
  .button {
  }
  .main-footer {
    justify-content: center;
  }
}
</style>
