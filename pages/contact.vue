<template>
  <div class="contactWrapper">
    <h1 class="contactWrapper__title">Want to talk with me?</h1>
    <h2 class="contactWrapper__subtitle">
      The best way is to ping me via email
      <a class="contactWrapper__link" href="mailto:dominik.ilnicki@gmail.com"
        >dominik.ilnicki@gmail.com</a
      >
      or twitter
      <a class="contactWrapper__link" href="https://twitter.com/dominikilnicki"
        >@dominikilnicki</a
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
    font-weight: 500;
  }

  .contactWrapper__subtitle {
    .contactWrapper__link {
      text-decoration: underline;
    }
  }
}
@media screen and (max-width: 720px) {
  .contactWrapper {
    max-width: 100%;
  }
}
</style>
