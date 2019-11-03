<template>
  <nav class="socialMenuWrapper">
    <ul class="list">
      <li class="list__element">
        <a
          class="element__link"
          href="https://www.linkedin.com/in/dominik-ilnicki/"
          target="_blank"
        >
          <i class="element__icon fab fa-linkedin-in"></i>
        </a>
      </li>
      <li class="list__element">
        <a
          class="element__link"
          href="https://twitter.com/DominikIlnicki"
          target="_blank"
        >
          <i class="element__icon fab fa-twitter"></i>
        </a>
      </li>
      <li class="list__element">
        <a
          class="element__link"
          href="https://github.com/Ilnicki010"
          target="_blank"
        >
          <i class="element__icon fab fa-github"></i>
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.socialMenuWrapper {
  position: relative;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
  .list {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    padding: 0 10px;
    .list__element {
      flex: 1;
      margin-top: 25px;
      .element__link .element__icon {
        padding: 7px;
        border-radius: 5px;
        transition: border-radius 0.2s ease-out, background-color 0.5s ease-out;
        &:hover {
          background: #baf2bb;
          border-radius: 100%;
        }
      }
    }
  }
}
@media screen and (max-width: 720px) {
  .socialMenuWrapper {
    display: none;
    .list {
      flex-direction: row;
    }
  }
}
</style>
