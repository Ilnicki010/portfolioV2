<template>
  <div class="contactWrapper">
    <h1>Want to talk with me?</h1>
    <h2>
      The best way is to ping me via email
      <a
        href="mailto:dominik.ilnicki@gmail.com"
      >dominik.ilnicki@gmail.com</a>
    </h2>
  </div>
</template>

<script>
export default {
  transition: 'default'
}
</script>

<style lang="scss" scoped>
.contactWrapper {
  display: flex;
  justify-content: center;
  height: calc(100vh - 160px);
  flex-direction: column;
  max-width: 60%;
  h1,
  p {
    margin: 0;
  }
  h1 {
    font-size: 1.2rem;
    font-weight: 500;
  }

  h2 {
    font-size: 2rem;
    a {
      text-decoration: underline;
    }
  }
}
@media screen and (max-width: 720px) {
  .contactWrapper {
    max-width: 100%;
    h1 {
      font-size: 1rem;
    }
    h2 {
      font-size: 1.4rem;
    }
  }
}
</style>
