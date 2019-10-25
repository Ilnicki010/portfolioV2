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
  }
}
</script>

<style lang="scss" scoped>
.mainWrapper {
  padding: 20px 70px;
  display: grid;
  grid-template-rows: 80vh 1fr;
  grid-template-columns: 1fr 1fr;
  grid-row-gap: 30px;
}
.cta-section {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 1;
  display: flex;
  justify-content: center;
  flex-direction: column;
  position: relative;

  .cta-section__navbar {
    display: flex;
    justify-content: center;

    img {
      flex: 1;
      max-width: 100px;
    }

    ul {
      flex: 4;
      display: flex;
      align-items: center;
      justify-content: flex-end;

      li {
        margin: 0 40px;
      }

      li a {
        color: #000;
        font-weight: 600;
      }
    }
  }

  .cta-section__content {
    flex: 6;
    max-width: 60%;
    display: flex;
    flex-direction: column;
    justify-content: center;

    h1 {
      font-size: 1.2rem;
      font-weight: 500;
    }

    h2 {
      font-size: 2rem;
    }

    .cta-section__content__buttons {
      margin-top: 50px;
      display: flex;
    }
  }

  .cta-section__navbar {
    flex: 1;
  }

  .pattern {
    position: absolute;
    top: -100px;
    right: -200px;
    z-index: -9999;
    max-width: 500px;
  }
}

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
