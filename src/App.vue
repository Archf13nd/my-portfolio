<template>
  <the-header :adjustNav="adjustNav"></the-header>
  <the-hero @heroRef="heroRef = $event"></the-hero>
  <the-intro></the-intro>
  <the-services></the-services>
  <the-services-mid-section></the-services-mid-section>
  <the-projects></the-projects>
  <the-about></the-about>
  <the-contact></the-contact>
  <the-footer></the-footer>
</template>

<script>
import TheHeader from "./components/UI/Header.vue";
import TheHero from "./components/Hero.vue";
import TheIntro from "./components/Intro.vue";
import TheServices from "./components/Services.vue";
import TheServicesMidSection from "./components/ServicesMidSection.vue";
import theProjects from "./components/Projects.vue";
import TheAbout from "./components/About.vue";
import TheContact from "./components/Contact.vue";
import TheFooter from "./components/UI/Footer.vue";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    TheIntro,
    TheServices,
    TheServicesMidSection,
    theProjects,
    TheAbout,
    TheContact,
    TheFooter
  },
  data() {
    return {
      adjustNav: false,
      heroRef: null
    };
  },
  methods: {},
  mounted() {
    const adjustNav = value => {
      this.adjustNav = value;
    };
    const element = this.heroRef;
    function createObserver() {
      let observer;

      let options = {
        root: null,
        rootMargin: "0px",
        threshold: 0.9
      };

      observer = new IntersectionObserver(entry => {
        if (!entry[0].isIntersecting) {
          adjustNav(true);
        } else {
          adjustNav(false);
        }
      }, options);
      observer.observe(element);
    }
    createObserver();
  }
};
</script>

<style lang="scss">
#app {
  display: grid;
  grid: min-content / calc(33.33vw / 2) 66.66vw calc(33.33vw / 2);
}

.hero {
  grid-column: 1 / 4;
}

.intro {
  grid-column: 2 / 3;
}

.services {
  grid-column: 2 / 3;
}
.services-mid-section {
  grid-column: 1 / 4;
}
.projects {
  grid-column: 2 / 3;
}
.about {
  grid-column: 2 / 3;
  // min-height: 100vh;
}
.contact {
  grid-column: 2 / 3;
}

.footer {
  grid-column: 1 / 4;
}

*,
::before,
::after {
  box-sizing: inherit;
}

:root {
  font-size: 50%;
}
@keyframes slideDown {
  from {
    top: 0;
  }

  to {
    top: 100;
  }
}

@keyframes flip {
  from {
    transform: translate(-50%, -50%) rotateX(-80deg);
    opacity: 0;
  }

  to {
    transform: translate(-50%, -50%) rotateX(0);
    opacity: 1;
  }
}
@keyframes flip-reverse {
  from {
    transform: translate(-50%, -50%) rotateX(0);
    opacity: 1;
  }

  to {
    transform: translate(-50%, -50%) rotateX(-80deg);

    opacity: 0;
  }
}
</style>
