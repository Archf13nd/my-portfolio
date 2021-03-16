<template>
  <div class="navbox">
    <div class="navbox__header">
      <ul class="navbox__tabs">
        <li class="navbox__tab" :class="{ 'navbox__tab--active': theActiveNav === 0 }" @click="activeNav = 0">
          ☻ Business
        </li>
        <li class="navbox__tab" :class="{ 'navbox__tab--active': theActiveNav === 1 }" @click="activeNav = 1">
          ☻ Expertise
        </li>
        <li class="navbox__tab" :class="{ 'navbox__tab--active': theActiveNav === 2 }" @click="activeNav = 2">
          ☻ Quality
        </li>
      </ul>
    </div>

    <transition name="fade" mode="out-in">
      <div class="navbox__tabOne" v-if="theActiveNav === 0">
        <div class="global__title navbox__title">What I can offer you</div>

        <p class="global__paragraph navbox__paragraph">
          I want you to know that trusting me with your site won't be a mistake. By working together I am confident we can meet your vision.
        </p>
        <p class="global__paragraph navbox__paragraph">
          Your needs come first and ultimately the site is for you. I will do everything in my power to make what you want possible.
        </p>

        <!-- <div class="percentageBar">
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
        </div> -->
      </div>

      <div class="navbox__tabTwo" v-else-if="theActiveNav === 1">
        <ul class="grid-list__items">
          <li class="grid-list__item">
            <h3 class="grid-list__number">1</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">HTML</span><br />
              SEO, performant, and accessible
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">2</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">CSS and SASS</span><br />
              Responsive, maintainable and optimized
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">3</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Javascript</span><br />
              Knowledge of all the advanced concepts and big-O
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">4</h3>
            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Framework</span><br />
              Currently love Vue.js but can work with any
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">5</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">NPM</span><br />
              I know when to and when not to use external packages
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">6</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Github</span><br />
              Knowledge of basic and advanced features
            </p>
          </li>
        </ul>
      </div>

      <div class="navbox__tabThree" v-else>
        <div class="info-box">
          <p class="global__paragraph info-box__paragraph">
            <span class="info-box__paragraph--bold">I strive for</span>
            perfection in my work. I'm passionate about web development and beleive in creating quality web content for everyone. For me it's not just about
            bringing to life a design, but to also go that one step further and make sure the site is opimized and discoverable.
          </p>
          <p class="global__paragraph info-box__paragraph">
            <span class="info-box__paragraph--bold">I offer you</span>
            my services for a competitive price but with no lack of quality. I don't just make websites for the money, I make them because I'm passionate about
            it.
          </p>

          <ul class="info-box__list">
            <li class="info-box__list-item">
              I strive to make the site noticed by search engines
            </li>
            <li class="info-box__list-item">
              I strive to have the site load in a split second
            </li>
            <li class="info-box__list-item">
              I strive for lightning fast navigation
            </li>
            <li class="info-box__list-item">
              I strive for smooth animations
            </li>
            <li class="info-box__list-item">
              I strive to make a great user experience
            </li>
          </ul>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeNav: 0
    };
  },
  computed: {
    theActiveNav() {
      return this.activeNav;
    }
  }
};
</script>

<style lang="scss" scoped>
a:active {
  color: $color-primary;
}

.grid-list {
  &__items {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    margin-top: -3rem;
  }

  &__item {
    flex: 0 0 50%;
    padding: 3rem 2rem 0 2rem;
    display: flex;
  }

  &__number {
    font-size: $font-size-title;
    color: $color-primary;
    margin-right: 1rem;
    height: fit-content;
    display: flex;
    align-items: flex-start;
    line-height: 1;
  }

  &__paragraph {
    &--bold {
      font-weight: bold;
    }
  }
}

.info-box {
  &__paragraph {
    &--bold {
      font-weight: bold;
    }
  }

  &__list {
    list-style: disc;
    display: inline-block;
    list-style-position: inside;

    > li {
      margin-top: 1rem;
    }
  }
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

  &__tabTwo {
    font-size: $font-size-text;
  }
  &__tabThree {
    font-size: $font-size-text;
  }

  &__tab--active {
    color: $color-primary;
  }

  &__title {
    line-height: 100%;
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

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in;
}
</style>
