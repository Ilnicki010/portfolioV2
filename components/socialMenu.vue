<template>
  <nav class="socialMenuWrapper">
    <ul>
      <li>
        <a href="https://www.linkedin.com/in/dominik-ilnicki/" target="_blank">
          <i class="fab fa-linkedin-in"></i>
        </a>
      </li>
      <li>
        <a href="https://twitter.com/DominikIlnicki" target="_blank">
          <i class="fab fa-twitter"></i>
        </a>
      </li>
      <li>
        <a href="https://github.com/Ilnicki010" target="_blank">
          <i class="fab fa-github"></i>
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
  ul {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    padding: 0 10px;
    li {
      flex: 1;
      margin-top: 25px;
      a i {
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
    ul {
      flex-direction: row;
    }
  }
}
</style>