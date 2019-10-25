// eslint-disable
<template>
  <nuxt-link
    v-if="project"
    :to="`/projects/${project.nameID}`"
    tag="article"
    class="projects-wrapper__project"
    :style="`background: ${project.mainColor}`"
  >
    <div class="project__header">
      <span class="project__label">{{ project.type }}</span>
      <h3 class="project__name">{{ project.name }}</h3>
    </div>
    <div
      class="project__photo"
      :style="{
        backgroundImage: 'url(' + getImgUrl(project.nameID) + ')'
      }"
    ></div>
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
  computed: {
    importedImg() {
      return require('@/assets/projects/kaligrafowane.png')
    }
  },
  mounted() {
    console.log(this.project.image)
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
  height: 400px;
  transition: transform 0.2s ease-in-out;
  .project__header {
    padding: 5px 30px;

    .project__label {
      opacity: 0.6;
    }
    .project__name {
      margin: 5px 0;
    }
  }

  .project__photo {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 75%;
    width: 80%;
    margin: 0 auto;
    border-radius: 10px 10px 0 0;
    background-position: center;
    background-size: cover;
    box-shadow: 0 0 40px rgba(0, 0, 0, 0.2);
    // background-image: url('../assets/projects/kaligrafowane.png');
  }
  &:hover {
    transform: translateY(-20px);
  }
}
</style>
