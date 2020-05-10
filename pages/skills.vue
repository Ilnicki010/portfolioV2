<template>
  <div class="skillsWrapper">
    <div class="skillsWrapper__content">
      <h1 class="content__title">What can I do for you?</h1>
      <h2 class="content__subtitle">
        I'm focused on front-end technologies, but back-end and UI/UX are also
        close to my heart
      </h2>
    </div>
    <section class="skillsWrapper__skills-section">
      <h3>My skills</h3>
      <div class="skills-section__list-wrapper">
        <ul class="list-wrapper__list">
          <li class="list__element">
            <img
              src="@/assets/stack-logos/javascript.svg"
              class="list__stack-logo"
              alt="js logo"
            />
            <span class="list__logo_desc">JavaScript</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/es6.svg"
              class="list__stack-logo"
              alt="es6 logo"
            />
            <span class="list__logo_desc">ES6</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/vue.svg"
              class="list__stack-logo"
              alt="vue logo"
            />
            <span class="list__logo_desc">Vue JS</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/react.svg"
              class="list__stack-logo"
              alt="react logo"
            />
            <span class="list__logo_desc">React</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/nuxt.svg"
              class="list__stack-logo"
              alt="nuxt logo"
            />
            <span class="list__logo_desc">Nuxt</span>
          </li>

          <li class="list__element">
            <img
              src="@/assets/stack-logos/html-5.svg"
              class="list__stack-logo"
              alt="html logo"
            />
            <span class="list__logo_desc">HTML5</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/sass.svg"
              class="list__stack-logo"
              alt="sass logo"
            />
            <span class="list__logo_desc">Scss</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/nodejs.svg"
              class="list__stack-logo"
              alt="node logo"
            />
            <span class="list__logo_desc">Node JS</span>
          </li>
          <li class="list__element">
            <img
              src="@/assets/stack-logos/adobe-xd.svg"
              class="list__stack-logo"
              alt="adobe xd logo"
            />
            <span class="list__logo_desc">Adobe XD</span>
          </li>
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
      font-weight: 500;
    }

    .content__subtitle {
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
          flex: 1;
          padding: 5px 1vw;
          margin: 5px 10px;
          animation: slide-down-fade 0.2s both ease-in-out;
          display: flex;
          align-items: center;
          justify-content: center;
          text-align: center;
          flex-direction: column;
          @for $i from 1 through 9 {
            &:nth-child(#{$i}) {
              animation-delay: #{$i * 0.1}s;
            }
          }
          .list__stack-logo {
            max-height: 5vh;
            margin-bottom: 7px;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 720px) {
  .skillsWrapper .skillsWrapper__content {
    max-width: 100%;
    .content__title {
    }
    .content__subtitle {
    }
  }
}
@keyframes slide-down-fade {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
