// eslint-disable
<template>
  <nuxt-link
    v-if="project"
    :to="`/projects?name=${project.nameID}`"
    tag="article"
    class="projects-wrapper__project"
    :style="`background: ${project.mainColor}`"
  >
    <div class="project__header">
      <span class="project__label">{{ project.type }}</span>
      <h3 class="project__name">{{ project.name }}</h3>
    </div>
    <div class="project__photoWrapper">
      <div
        class="project__photo"
        :style="{
          backgroundImage: 'url(' + getImgUrl(project.nameID) + ')'
        }"
      ></div>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    project: {
      type: Object,
      default: null
    }
  },
  methods: {
    getImgUrl(projectName) {
      const images = require.context('../assets/projects/', false, /\.png$/)
      return images('./' + projectName + '.png')
    }
  }
}
</script>

<style lang="scss" scoped>
.projects-wrapper__project {
  cursor: pointer;
  position: relative;
  padding: 20px;
  border-radius: 10px;
  flex: 1;
  display: flex;
  flex-direction: column;
  height: 400px;
  max-width: 100%;
  transition: transform 0.2s ease-in-out;
  .project__header {
    padding: 5px 30px;
    flex: 1;
    .project__label {
      opacity: 0.6;
    }
    .project__name {
      margin: 5px 0;
    }
  }
  .project__photoWrapper {
    position: relative;
    flex: 3;
    .project__photo {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding-bottom: 56.25%;
      margin: 0 auto;
      border-radius: 10px;
      background-position: center;
      background-size: cover;
      box-shadow: 0 -4px 10px rgba(0, 0, 0, 0.2);
    }
  }
  &:hover {
    transform: translateY(-20px);
  }
}
@media screen and (max-width: 720px) {
  .projects-wrapper__project {
    height: 40vh;
    .project__photo {
      height: 55%;
    }
  }
}
</style>
