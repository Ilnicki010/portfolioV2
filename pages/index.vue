<template>
  <div class="mainWrapper">
    <header class="cta-section">
      <nav class="cta-section__navbar">
        <img src="@/assets/logo.svg" alt="Dominik Ilnicki Logo" />
        <ul class="main-menu">
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
      </nav>
      <div class="cta-section__content">
        <h1>Dominik Ilnicki web developer based in Gdynia Poland</h1>
        <h2>
          Hi I’m working on web projects to make user experiences best as it is
          possible
        </h2>
        <div class="cta-section__content__buttons">
          <a href class="button button--primary">Contact me</a>
          <a
            href="https://github.com/Ilnicki010"
            target="_blank"
            class="button button--ghost"
            >GitHub</a
          >
        </div>
      </div>
      <img src="@/assets/patter.svg" class="pattern" alt="decoral pattern" />
    </header>
    <main class="projects-wrapper">
      <project-block
        v-for="project in myProjects"
        :key="project.id"
        :project="project"
      />
    </main>
    <footer class="main-footer">© Dominik Ilnicki 2019</footer>
  </div>
</template>

<script>
import myProjects from '@/static/projects.json'
import projectBlock from '@/components/projectBlock'
export default {
  components: { projectBlock },
  data() {
    return {
      myProjects
    }
  },
  mounted() {
    console.log(this.myProjects)
  }
}
</script>

<style lang="scss" scoped>
.projects-wrapper {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: 2;
  display: grid;
  grid-template-rows: auto;
  grid-template-columns: 1fr 1fr;
  grid-gap: 40px;
}
</style>
