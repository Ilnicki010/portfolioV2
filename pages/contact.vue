<template>
  <div class="contactWrapper">
    <h1 class="contactWrapper__title">Want to talk with me?</h1>
    <h2 class="contactWrapper__subtitle">
      The best way is to ping me via email
      <a class="contactWrapper__mail" href="mailto:dominik.ilnicki@gmail.com"
        >dominik.ilnicki@gmail.com</a
      >
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
  .contactWrapper__title {
    margin: 0;
    font-size: 1.2rem;
    font-weight: 500;
  }

  .contactWrapper__subtitle {
    font-size: 2rem;
    .contactWrapper__mail {
      text-decoration: underline;
    }
  }
}
@media screen and (max-width: 720px) {
  .contactWrapper {
    max-width: 100%;
    .contactWrapper__title {
      font-size: 1rem;
    }
    .contactWrapper__subtitle {
      font-size: 1.4rem;
    }
  }
}
</style>
