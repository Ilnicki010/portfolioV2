<template>
  <div class="skillsWrapper">
    <div class="skillsWrapper__content">
      <h1>What can I do for you?</h1>
      <h2>I'm trying to learn a lot of technologies all the time. I pay attention to performance, accessibility and UI/UX of my web apps.</h2>
    </div>
    <section class="skillsWrapper__skills-section">
      <h3>My skills</h3>
      <div class="skills-section__list-wrapper">
        <ul class="list-wrapper__list">
          <li>JS</li>
          <li>VUE</li>
          <li>NUXT</li>
          <li>ES6</li>
          <li>HTML</li>
          <li>SCSS</li>
          <li>UI/UX</li>
          <li>Node</li>
          <li>Adobe XD</li>
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
    h1 {
      font-size: 1.2rem;
      font-weight: 500;
    }

    h2 {
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
        li {
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
    h1 {
      font-size: 1rem;
    }
    h2 {
      font-size: 1.4rem;
    }
  }
}
</style>