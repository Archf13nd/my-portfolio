<template>
  <div class="navbox">
    <div class="navbox__header">
      <ul class="navbox__tabs">
        <li
          class="navbox__tab"
          :class="{ 'navbox__tab--active': theActiveNav === 0 }"
          @click="activeNav = 0"
        >
          Business
        </li>
        <li
          class="navbox__tab"
          :class="{ 'navbox__tab--active': theActiveNav === 1 }"
          @click="activeNav = 1"
        >
          Expertise
        </li>
        <li
          class="navbox__tab"
          :class="{ 'navbox__tab--active': theActiveNav === 2 }"
          @click="activeNav = 2"
        >
          Quality
        </li>
      </ul>
    </div>

    <div class="navbox__tabOne" v-if="theActiveNav === 0">
      <div class="global__title navbox__title">What I can offer you</div>

      <p class="global__paragraph navbox__paragraph">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem vitae cum
        in molestiae magnam pariatur fuga iure perspiciatis obcaecati excepturi,
        dolorum beatae? Amet, accusantium.
      </p>

      <div class="percentageBar">
        <div class="percentageBar__title">Title one</div>
        <div class="percentageBar__bar">
          <div class="percentageBar__bar-fill percentageBar__bar--1"></div>
        </div>
      </div>
      <div class="percentageBar">
        <div class="percentageBar__title">Title two</div>
        <div class="percentageBar__bar">
          <div class="percentageBar__bar-fill percentageBar__bar--2"></div>
        </div>
      </div>
      <div class="percentageBar">
        <div class="percentageBar__title">Title three</div>
        <div class="percentageBar__bar">
          <div class="percentageBar__bar-fill percentageBar__bar--3"></div>
        </div>
      </div>
    </div>

    <div class="navbox__tabTwo" v-if="theActiveNav === 1">
      <h1>Hi</h1>
    </div>

    <div class="navbox__tabThree" v-if="theActiveNav === 2">
      <h1>Kill</h1>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeNav: 0,
    };
  },
  computed: {
    theActiveNav() {
      return this.activeNav;
    },
  },
};
</script>

<style lang="scss" scoped>
a:active {
  color: $color-primary;
}

.navbox {
  &__header {
    margin-bottom: 3rem;
    & > ul {
      display: flex;
      justify-content: space-between;
      font-size: $font-size-title--sub;
      font-weight: bold;

      & > li {
        transition: all 0.15s ease-in;
        cursor: pointer;
        &:hover {
          color: $color-primary;
        }
      }
    }
  }

  &__tab--active {
    color: $color-primary;
  }

  &__title {
  }

  &__paragraph {
    margin: 2rem 0;
  }
}

.percentageBar {
  font-size: $font-size-label;
  font-weight: bold;
  margin-bottom: 2rem;

  &__bar {
    position: relative;
    width: 100%;
    height: 3rem;
    background: $color-light-shade;
    border-radius: 5px;

    &--1 {
      width: 40%;
    }
    &--2 {
      width: 77%;
    }
    &--3 {
      width: 66%;
    }
  }
  &__bar-fill {
    height: 100%;
    background: $color-primary;
    position: absolute;
    border-radius: inherit;
    top: 0;
    left: 0;
  }
}
</style>
