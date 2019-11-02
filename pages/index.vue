<template>
  <div class="mainWrapper">
    <header class="cta-section">
      <div class="cta-section__content">
        <h1>Dominik Ilnicki, web developer based in Gdynia Poland</h1>
        <h2>Hi I’m working on web projects to make users experiences as best as it is possible</h2>
        <div class="cta-section__content__buttons">
          <nuxt-link to="/contact" class="button button--primary">Contact me</nuxt-link>
          <a
            href="https://github.com/Ilnicki010"
            target="_blank"
            class="button button--ghost button--github"
          >
            <i class="fab fa-github"></i>
            GitHub
          </a>
        </div>
      </div>
      <img src="@/assets/patter.svg" class="pattern" alt="decoral pattern" />
      <img src="@/assets/patter.svg" class="pattern" alt="decoral pattern" />
    </header>
    <social-menu class="social-menu" />
    <main class="projects-wrapper">
      <project-block v-for="project in myProjects" :key="project.nameID" :project="project" />
    </main>
  </div>
</template>

<script>
import myProjects from '@/static/projects.json'
import projectBlock from '@/components/projectBlock'
import socialMenu from '@/components/socialMenu'
export default {
  transition: 'default',
  components: { projectBlock, socialMenu },
  data() {
    return {
      myProjects
    }
  }
}
</script>

<style lang="scss" scoped>
.mainWrapper {
  display: grid;
  grid-template-rows: 75vh 1fr;
  grid-template-columns: 3fr 1fr;
  grid-row-gap: 30px;
  overflow-x: hidden;
  position: relative;
}
.social-menu {
  grid-column-start: 2;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 1;
  display: block;
}
.cta-section {
  grid-column-start: 1;
  grid-column-end: 1;
  grid-row-start: 1;
  grid-row-end: 1;
  display: flex;
  justify-content: center;
  flex-direction: column;
  position: relative;

  .cta-section__content {
    flex: 6;
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
      .button:first-child {
        margin-right: 25px;
      }
    }
  }

  .pattern {
    display: none;
    // position: absolute;
    // top: 0;
    // right: 0;
    // z-index: -9999;
    // width: 200px;
    // &:last-child {
    //   top: 20px;
    //   right: 40px;
    //   z-index: -9999;
    //   width: 230px;
    //   transform: rotate(-24deg);
    // }
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
  padding: 0 10px;
  margin-bottom: 30px;
}
@media screen and (max-width: 720px) {
  .mainWrapper {
    grid-template-rows: 20px 65vh 1fr;
    grid-template-columns: 3fr 1fr;
    grid-gap: 10px;
  }
  .social-menu {
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 1;
    align-items: flex-start;
    display: none;
  }
  .cta-section {
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 2;
    grid-row-end: 2;
    .cta-section__navbar {
      ul {
        flex-direction: column;
        li {
          margin: 0 5px;
        }
      }
    }
    .cta-section__content {
      min-width: 100%;
      h1 {
        font-size: 1rem;
      }
      h2 {
        font-size: 1.4rem;
      }
      .cta-section__content__buttons {
        justify-content: flex-start;
      }
    }
  }

  .projects-wrapper {
    grid-gap: 40px;
    grid-template-columns: auto;
    grid-column-start: 1;
    grid-row-start: 3;
    grid-row-end: 3;
  }
}
.button--github {
  i {
    margin-right: 10px;
  }
}
</style>
