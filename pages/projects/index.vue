<template>
  <div class="projectWrapper">
    <div class="back-link">
      <nuxt-link to="/" class="back-link__link">
        <i class="back-link__icon fas fa-angle-left"></i>Back
      </nuxt-link>
    </div>
    <div class="projectWrapper__image-wrapper" :style="`background:${mainColor}`">
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
      <a :href="liveDemoLink" target="_blank" class="button button--primary">Visit site</a>
      <a :href="ghLink" target="_blank" class="buttons__icon button button--ghost button--github">
        <i class="fab fa-github"></i>
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
          >{{ item }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import myProjects from '@/static/projects.json'
export default {
  transition: 'default',
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
  },
  computed: {
    borderLeft() {
      return `border-left:1.4px solid ${this.mainColor}`
    }
  }
}
</script>
<style lang="scss" scoped>
.projectWrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 48px auto auto;
  grid-gap: 40px;
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
    height: 50vh;
    padding: 20px;
    .image-wrapper__parent {
      position: relative;
      display: flex;
      width: 100%;
      height: 100%;
      .image-wrapper__parent__image {
        position: absolute;
        margin: 20px;
        bottom: 0;
        left: 0;
        right: 0;
        padding-bottom: 56.25%;
        margin: 0 auto;
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
      margin-right: 35px;
    }
    .button .buttons__icon {
      margin-right: 10px;
    }
  }
  .projectWrapper__content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    .content__field {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      margin-bottom: 30px;
      * {
        margin: 0;
      }
      .field__label {
        opacity: 0.4;
        font-size: 0.8rem;
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
          font-size: 0.9rem;
          margin: 5px 10px;
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
