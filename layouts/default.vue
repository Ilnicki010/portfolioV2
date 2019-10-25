<template>
  <div>
    <nuxt />
    <footer class="main-footer">© Dominik Ilnicki 2019</footer>
  </div>
</template>

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
}

.button {
  border-radius: 4px;
  width: 160px;
  height: 48px;
  text-align: center;
  position: relative;
  padding: 10px 20px;
  margin: 0 20px;
  display: block;
  display: flex;
  justify-content: center;
  align-items: center;

  &::after {
    content: '';
    position: absolute;
    top: -5px;
    left: 6px;
    width: 100%;
    height: 100%;
    z-index: -9999;
    border-radius: inherit;
    transition: all 0.2s ease-in-out;
  }

  &:hover {
    &::after {
      transform: translate(-6px, 5px);
      border-color: transparent;
    }
  }
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
  border: 2px solid #000;

  &::after {
    content: '';
    background: transparent;
    border: inherit;
  }
}

.main-footer {
  padding: 30px 90px;
  font-weight: 800;
  display: flex;
  align-items: center;
}
</style>
