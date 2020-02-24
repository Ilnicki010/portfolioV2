<template>
  <div class="projectWrapper">
    <div class="back-link">
      <nuxt-link to="/" class="back-link__link">
        <i class="back-link__icon fas fa-angle-left"></i>Back
      </nuxt-link>
    </div>
    <div
      class="projectWrapper__image-wrapper"
      :style="`background:${mainColor}`"
    >
      <div class="image-wrapper__parent">
        <div
          class="image-wrapper__parent__image"
          :style="{
            backgroundImage: `url(${getImgUrl(nameID)}`
          }"
        ></div>
      </div>
    </div>
    <div class="projectWrapper__buttons">
      <a :href="liveDemoLink" target="_blank" class="button button--primary"
        >Visit site</a
      >
      <a
        :href="ghLink"
        target="_blank"
        class="buttons__icon button button--ghost button--github"
      >
        <span class="button__icon fab fa-github" aria-hidden="true"></span>
        Code
      </a>
    </div>
    <div class="projectWrapper__content">
      <div class="content__field">
        <span class="field__label">Project name</span>
        <h1 class="field__name">{{ name }}</h1>
      </div>
      <div class="content__field">
        <span class="field__label">Description</span>
        <p class="field__desc">{{ description }}</p>
      </div>
      <div class="content__field">
        <span class="field__label">Stack</span>
        <ul class="field__stack-list">
          <li
            v-for="item in stack"
            :key="stack.indexOf(item)"
            class="stack-list__element"
            :style="borderLeft"
          >
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import myProjects from '@/static/projects.json'
export default {
  transition: 'default',
  computed: {
    borderLeft() {
      return `border-left:1.4px solid ${this.mainColor}`
    }
  },
  asyncData({ params, env, error, query }) {
    const project = myProjects.find(
      (project) => String(project.nameID) === query.name
    )
    if (!project) {
      return error({ message: 'Project not found', statusCode: 404 })
    }

    return project
  },
  methods: {
    getImgUrl(projectName) {
      const images = require.context('@/assets/projects/', false, /\.png$/)
      return images(`./${projectName}.png`)
    }
  }
}
</script>
<style lang="scss" scoped>
.projectWrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 12vh 50vh auto;
  grid-gap: 48px;
  width: 100%;
  .back-link {
    grid-column-start: 1;
    grid-column-end: 4;
    display: flex;
    align-items: center;
    font-weight: 900;
    color: #000;
    .back-link__link {
      color: #000;
    }
    .back-link__icon {
      margin-right: 10px;
    }
  }
  .projectWrapper__image-wrapper {
    border-radius: 10px;
    position: relative;
    padding: 0 3%;
    height: 90%;
    .image-wrapper__parent {
      position: relative;
      display: flex;
      width: 100%;
      height: 100%;
      .image-wrapper__parent__image {
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        right: 0;
        height: 80%;
        margin: auto;
        border-radius: 10px;
        background-position: center;
        background-size: cover;
        box-shadow: 0 0 40px rgba(0, 0, 0, 0.2);
      }
    }
  }
  .projectWrapper__buttons {
    grid-column-start: 1;
    grid-column-end: 1;
    grid-row-start: 3;
    grid-row-end: 3;
    display: flex;
    justify-content: center;
    .button:first-child {
      margin-right: 10%;
    }
    .button .buttons__icon {
      margin-right: 10px;
    }
  }
  .projectWrapper__content {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    padding-left: 1.6vw;
    .content__field {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      margin-bottom: 30px;
      * {
        margin: 0;
      }
      .field__name {
        font-size: 1.7em;
      }
      .field__label {
        opacity: 0.4;

        padding-bottom: 10px;
      }
      .field__stack-list {
        padding: 0;
        display: inline-flex;
        justify-content: flex-start;
        flex-wrap: wrap;
        .stack-list__element {
          padding: 5px 10px;
          text-align: center;

          margin: 1% 2%;
        }
      }
    }
  }
}
@media screen and (max-width: 720px) {
  .projectWrapper {
    grid-template-columns: 1fr;
    grid-template-rows: 48px auto auto;
    grid-row-gap: 40px;
    grid-column-gap: 0;
    .back-link {
      margin-bottom: -40px;
    }
    .projectWrapper__image-wrapper {
      grid-column-start: 1;
      grid-column-end: 2;
      grid-row-start: 3;
      grid-row-end: 3;
      height: 200px;
    }
    .projectWrapper__buttons {
      grid-column-start: 1;
      grid-column-end: 2;
      grid-row-start: 5;
      grid-row-end: 5;
      justify-content: space-between;
      .button {
        flex: 1;
      }
    }
    .projectWrapper__content {
      grid-column-start: 1;
      grid-column-end: 2;
      grid-row-start: 4;
      grid-row-end: 4;
    }
  }
}
</style>
