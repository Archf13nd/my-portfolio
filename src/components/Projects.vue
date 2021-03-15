<template>
  <div class="projects" id="projects">
    <h3 class="global__section-title project">projects</h3>
    <h1 class="global__title">Projects I'm proud of</h1>
    <div class="projects__gallery">
      <div class="projects__gallery__project-0" id="0" @click="openProject"></div>
    </div>
    <!-- Background overlay for project card -->
    <transition name="fade">
      <div class="projects__card--overlay" v-if="projectOpen"></div>
    </transition>
    <transition name="flip">
      <project-card
        v-if="projectOpen && project === '0'"
        @close="closeProject"
        :img="`https://cdn.pixabay.com/photo/2011/12/14/12/21/orion-nebula-11107_960_720.jpg`"
        :title="`Vue App`"
        :titleSub="`It's an app ok`"
        :paragraphOne="
          'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore, mollitia? Ipsam ipsa fugiat laboriosam pariatur voluptate accusamus eum?'
        "
        :paragraphTwo="
          'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore, mollitia? Ipsam ipsa fugiat laboriosam pariatur voluptate accusamus eum?'
        "
        :paragraphQuote="'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore, mollitia? Ipsam ipsa fugiat ?'"
      ></project-card>
    </transition>
  </div>
</template>

<script>
import ProjectCard from "./UI/ProjectCard.vue";
export default {
  components: {
    ProjectCard
  },
  data() {
    return {
      projectOpen: false,
      project: 0
    };
  },
  methods: {
    openProject(e) {
      this.project = e.target.id;
      this.projectOpen = true;
    },
    closeProject() {
      this.projectOpen = false;
    }
  }
};
</script>

<style lang="scss" scoped>
.projectCard {
  z-index: 102;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 60vw;
  height: 60vh;
}
.projects {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 13rem;

  &__card--overlay {
    z-index: 101;
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.8);
  }

  &__gallery {
    margin-top: 10rem;
    width: 100%;
    display: grid;
    gap: 1rem;
    justify-content: center;
    grid: repeat(auto-fill, 35rem) / repeat(auto-fit, 35rem);

    & > div {
      width: 100%;
      height: 100%;
      border: 4px solid $color-black;

      &:hover {
        background-size: 220%;
      }
    }

    &__project-0 {
      background: no-repeat center / cover content-box url("../assets/img/message-app.png");
    }
  }
}

// Transition for project card

.flip-enter-from {
}

.flip-enter-active {
  animation: flip 0.3s ease-in forwards;
}
.flip-leave-active {
  animation: flip-reverse 0.3s ease-in forwards;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}
</style>
