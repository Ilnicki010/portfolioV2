<template>
  <div class="contactWrapper">
    <h1>Want to talk with me?</h1>
    <h2>
      The best way to ping me is through the mail dominik.ilnicki@gmail.com
    </h2>
  </div>
</template>

<script>
import mainMenu from '@/components/mainMenu'
export default {
  components: { mainMenu }
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
