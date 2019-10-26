<template>
  <div class="main-menu">
    <input type="checkbox" />
    <span></span>
    <span></span>
    <span></span>
    <ul class="main-menu__content">
      <li>
        <a href>Contact me</a>
      </li>
      <li>
        <a href>My projects</a>
      </li>
      <li>
        <a href>Skills</a>
      </li>
      <li>
        <a href>Resume</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.main-menu {
  flex: 4;
  display: flex;
  align-items: center;
  justify-content: flex-end;

  input {
    display: none;
  }
  ul {
    display: flex;
    li {
      margin: 0 40px;
    }

    li a {
      color: #000;
      font-weight: 600;
      padding: 10px 0;
      border-bottom: 2px solid transparent;
      transition: border-bottom 0.3s ease-out;
      &:hover {
        transform: translateY(0);
        border-bottom-color: #000;
      }
    }
  }
}
@media screen and (max-width: 720px) {
  .main-menu {
    position: relative;
    .main-menu__content {
      position: absolute;
      transform-origin: 0% 0%;
      transform: translate(100vh, 0);
      width: calc(100% + 160px);
      height: 100vh;
      margin: auto;
      top: 0;
      left: -130px;
      z-index: 9999;
      border-radius: 4px;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #000000;
      background-image: url("data:image/svg+xml,%3Csvg width='52' height='26' viewBox='0 0 52 26' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23baf2bb' fill-opacity='0.1'%3E%3Cpath d='M10 10c0-2.21-1.79-4-4-4-3.314 0-6-2.686-6-6h2c0 2.21 1.79 4 4 4 3.314 0 6 2.686 6 6 0 2.21 1.79 4 4 4 3.314 0 6 2.686 6 6 0 2.21 1.79 4 4 4v2c-3.314 0-6-2.686-6-6 0-2.21-1.79-4-4-4-3.314 0-6-2.686-6-6zm25.464-1.95l8.486 8.486-1.414 1.414-8.486-8.486 1.414-1.414z' /%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
      font-size: 2rem;
      transition: transform 0.2s ease-out;
      li {
        padding: 20px;
        width: 100%;
        font-size: 1.2rem;
        cursor: pointer;
        &:last-child {
          margin: auto;
          display: block;
          position: absolute;
          bottom: 30px;
          left: 0;
          background: #baf2bb;
          text-align: center;
          a {
            color: #000;
          }
        }
        a {
          color: #fff;
        }
      }
    }

    input {
      height: 48px;
      width: 48px;
      display: block;
      position: absolute;
      margin: 0;
      padding: 0;
      opacity: 0;
      z-index: 99999999;
      transform-origin: 50% 50%;
      &:checked ~ span {
        background: #fff;
        z-index: 9999999;
      }
      &:checked ~ span:nth-child(2) {
        transform: translate(0, 0) rotate(45deg);
      }
      &:checked ~ span:nth-child(3) {
        opacity: 0;
      }
      &:checked ~ span:nth-child(4) {
        transform: translate(0, 0) rotate(-45deg);
      }
      &:checked ~ .main-menu__content {
        transform: translate(0);
      }
    }
    span {
      display: block;
      position: absolute;
      width: 48px;
      height: 3px;
      background: #222;
      border-radius: 20px;
      transition: transform 0.2s ease-in-out, opacity 0.1s ease-in-out;
      transform-origin: center;
      &:nth-child(2) {
        transform: translateY(12px);
      }
      &:nth-child(4) {
        transform: translateY(-12px);
      }
    }
  }
}
</style>