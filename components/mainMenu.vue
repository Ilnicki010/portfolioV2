<template>
  <nav class="mainMenuWrapper">
    <nuxt-link to="/" class="logo">
      <logo class="logo__image" />
    </nuxt-link>
    <button
      class="hamburger"
      aria-expanded="false"
      :class="{ 'hamburger--active': openMenu }"
      @click="menuShowAndClose"
    >
      <span class="sr-only">Open/Close menu</span>
      <span class="hamburger__box">
        <span class="hamburger__inner"></span>
      </span>
    </button>
    <div class="navigation" :class="{ 'navigation--active': openMenu }">
      <ul class="navigation__list">
        <li class="navigation__item" @click="menuShowAndClose">
          <nuxt-link class="item__link" to="/">My projects</nuxt-link>
        </li>
        <li class="navigation__item" @click="menuShowAndClose">
          <nuxt-link class="item__link" to="/contact">Contact me</nuxt-link>
        </li>
        <li class="navigation__item" @click="menuShowAndClose">
          <nuxt-link class="item__link" to="/skills">Skills</nuxt-link>
        </li>
        <li class="navigation__item" @click="menuShowAndClose">
          <a
            class="item__link"
            href="https://docs.google.com/document/d/1aMHUhf3c8JjVaWm9NJgwtGxaxgKDkfKA6fSrQGBtLDs/edit"
            target="_blank"
          >
            Resume
            <i class="fas fa-external-link-alt"></i>
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import Logo from '@/components/Logo'
export default {
  components: { Logo },
  data() {
    return {
      openMenu: false
    }
  },
  methods: {
    menuShowAndClose() {
      this.openMenu ? (this.openMenu = false) : (this.openMenu = true)
    }
  }
}
</script>

<style lang="scss" scoped>
.mainMenuWrapper {
  display: flex;
  justify-content: space-between;
}
.logo {
  flex: 1;
}
.hamburger {
  display: none;
}
.navigation {
  flex: 3;
}

.navigation__list {
  display: flex;
  justify-content: space-around;
  align-items: center;
  list-style: none;
}

.navigation__item {
  .item__link {
    text-decoration: none;
    color: #000;
  }
}

.sr-only {
  border: 0;
  clip: rect(0, 0, 0, 0);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}
@media screen and (max-width: 720px) {
  .hamburger {
    padding: 10px;
    display: inline-block;
    cursor: pointer;
    background-color: transparent;
    border: 0;
    margin: 0;
    z-index: 999;
  }

  .hamburger,
  .navigation {
    transition: transform 0.2s 0.1s ease-in-out, visibility 0.2s 0.4s;
  }
  .hamburger__box {
    width: 35px;
    height: 24px;
    display: inline-block;
    position: relative;
  }
  @mixin hamburger-line {
    width: 100%;
    height: 3px;
    border-radius: 10px;
    background-color: #000;
    position: absolute;
  }

  .hamburger__inner {
    @include hamburger-line;

    left: 0;
    top: 50%;
    transform: translateY(-50%);
    transition: background-color 0.1s 0.2s ease-in-out;
  }

  .hamburger__inner::before,
  .hamburger__inner::after {
    @include hamburger-line;

    content: '';
    left: 0;
    transition: transform 0.2s 0.2s ease-in-out;
  }

  .hamburger__inner::before {
    top: -10px;
  }

  .hamburger__inner::after {
    top: 10px;
  }

  .hamburger--active .hamburger__inner {
    background-color: transparent;
  }

  .hamburger--active .hamburger__inner:before {
    transform: translateY(10px) rotate(45deg);
  }

  .hamburger--active .hamburger__inner:after {
    transform: translateY(-10px) rotate(-45deg);
  }
  .navigation {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    bottom: 0;
    height: 100vh;
    width: 100vw;
    right: 0;
    visibility: hidden;
    background: #fff;
    z-index: 99;
    transform: translateY(100vh);
  }
  .navigation--active {
    transition: transform 0.3s 0.1s ease-in-out, visibility 0s 0s;
    transform: translateY(0px);
    visibility: visible;
  }
  .navigation__list {
    padding: 0;
    display: flex;
    height: 70%;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
  }

  .navigation__item {
    .item__link {
      padding: 20px;
      text-decoration: none;
      color: #000;
      font-weight: 600;
      font-size: 1.6rem;
    }
  }
}
</style>
