<template>
  <div class="mainWrapper">
    <header class="cta-section">
      <div class="cta-section__content">
        <h1 class="content__title">
          Dominik Ilnicki, web developer based in Gdynia Poland
        </h1>
        <h2 class="content__subtitle">
          Hi, I’m working on web projects to make users experiences as best as
          it is possible
        </h2>
        <div class="cta-section__content__buttons">
          <nuxt-link to="/contact" class="button button--primary"
            >Contact me</nuxt-link
          >
          <a
            href="https://github.com/Ilnicki010"
            target="_blank"
            class="button button--ghost button--github"
          >
            <i class="button__icon fab fa-github"></i>
            GitHub
          </a>
        </div>
      </div>
    </header>
    <the-social-menu class="social-menu" />
    <main class="projects-wrapper">
      <single-project-element
        v-for="project in myProjects"
        :key="project.nameID"
        :project="project"
      />
    </main>
  </div>
</template>

<script>
import myProjects from '@/static/projects.json'
import SingleProjectElement from '@/components/SingleProjectElement'
import TheSocialMenu from '@/components/TheSocialMenu'
export default {
  transition: 'default',
  components: { SingleProjectElement, TheSocialMenu },
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

    .content__title {
      font-size: 1.2rem;
      font-weight: 500;
    }

    .content__subtitle {
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
  }
  .cta-section {
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 2;
    grid-row-end: 2;
    .cta-section__content {
      min-width: 100%;
      .content__title {
        font-size: 1rem;
      }
      .content__subtitle {
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
  .button__icon {
    margin-right: 10px;
  }
}
</style>
