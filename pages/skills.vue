<template>
  <div class="skillsWrapper">
    <div class="skillsWrapper__content">
      <h1 class="content__title">What can I do for you?</h1>
      <h2 class="content__subtitle">
        I'm focused on front end technologies, but backend stack and UI/UX are
        also close to my heart. It means that I develop complexive web
        applications.
      </h2>
    </div>
    <section class="skillsWrapper__skills-section">
      <h3>My skills</h3>
      <div class="skills-section__list-wrapper">
        <ul class="list-wrapper__list">
          <li class="list__element">JS</li>
          <li class="list__element">VUE</li>
          <li class="list__element">NUXT</li>
          <li class="list__element">ES6</li>
          <li class="list__element">HTML</li>
          <li class="list__element">SCSS</li>
          <li class="list__element">UI/UX</li>
          <li class="list__element">Node</li>
          <li class="list__element">Adobe XD</li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  transition: 'default'
}
</script>

<style lang="scss" scoped>
.skillsWrapper {
  display: flex;
  justify-content: center;
  height: calc(100vh - 160px);
  flex-direction: column;
  .skillsWrapper__content {
    max-width: 60%;
    .content__title {
      font-size: 1.2rem;
      font-weight: 500;
    }

    .content__subtitle {
      font-size: 2rem;
    }
  }
  .skillsWrapper__skills-section {
    .skills-section__list-wrapper {
      .list-wrapper__list {
        padding: 0;
        display: inline-flex;
        justify-content: flex-start;
        flex-wrap: wrap;
        .list__element {
          padding: 5px 13px;
          text-align: center;
          border-radius: 100px;
          font-size: 0.9rem;
          margin: 5px 10px;
          background: #baf2bb;
        }
      }
    }
  }
}
@media screen and (max-width: 720px) {
  .skillsWrapper .skillsWrapper__content {
    max-width: 100%;
    .content__title {
      font-size: 1rem;
    }
    .content__subtitle {
      font-size: 1.4rem;
    }
  }
}
</style>
