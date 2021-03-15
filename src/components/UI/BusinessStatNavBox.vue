<template>
  <div class="navbox">
    <div class="navbox__header">
      <ul class="navbox__tabs">
        <li
          class="navbox__tab"
          :class="{ 'navbox__tab--active': theActiveNav === 0 }"
          @click="activeNav = 0"
        >
          ☻ Business
        </li>
        <li
          class="navbox__tab"
          :class="{ 'navbox__tab--active': theActiveNav === 1 }"
          @click="activeNav = 1"
        >
          ☻ Expertise
        </li>
        <li
          class="navbox__tab"
          :class="{ 'navbox__tab--active': theActiveNav === 2 }"
          @click="activeNav = 2"
        >
          ☻ Quality
        </li>
      </ul>
    </div>

    <transition name="fade" mode="out-in">
      <div class="navbox__tabOne" v-if="theActiveNav === 0">
        <div class="global__title navbox__title">What I can offer you</div>

        <p class="global__paragraph navbox__paragraph">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem vitae cum
          in molestiae magnam pariatur fuga iure perspiciatis obcaecati
          excepturi, dolorum beatae? Amet, accusantium.
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

      <div class="navbox__tabTwo" v-else-if="theActiveNav === 1">
        <ul class="grid-list__items">
          <li class="grid-list__item">
            <h3 class="grid-list__number">1</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Lorem ipsum dolor</span>
              sit amet consectetur adipisicing elit.
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">2</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Lorem ipsum dolor</span>
              sit amet consectetur adipisicing elit.
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">3</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Lorem ipsum dolor</span>
              sit amet consectetur adipisicing elit.
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">4</h3>
            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Lorem ipsum dolor</span>
              sit amet consectetur adipisicing elit.
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">5</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Lorem ipsum dolor</span>
              sit amet consectetur adipisicing elit.
            </p>
          </li>
          <li class="grid-list__item">
            <h3 class="grid-list__number">6</h3>

            <p class="grid-list__paragraph">
              <span class="grid-list__paragraph--bold">Lorem ipsum dolor</span>
              sit amet consectetur adipisicing elit.
            </p>
          </li>
        </ul>
      </div>

      <div class="navbox__tabThree" v-else>
        <div class="info-box">
          <p class="info-box__paragraph">
            <span class="info-box__paragraph--bold"> We strive to achieve</span>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate
            sed illo quis nemo distinctio assumenda sapiente labore earum fugit
            error?
          </p>
          <p class="info-box__paragraph">
            <span class="info-box__paragraph--bold">Our goal is to help</span>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate
            sed illo quis nemo distinctio assumenda sapiente labore earum fugit
            error?
          </p>

          <ul class="info-box__list">
            <li class="info-box__list-item">
              Lorem ipsum dolor sit amet consectetur adipisicing.
            </li>
            <li class="info-box__list-item">
              Lorem ipsum dolor sit amet consectetur adipisicing.
            </li>
            <li class="info-box__list-item">
              Lorem ipsum dolor sit amet consectetur adipisicing.
            </li>
            <li class="info-box__list-item">
              Lorem ipsum dolor sit amet consectetur adipisicing.
            </li>
            <li class="info-box__list-item">
              Lorem ipsum dolor sit amet consectetur adipisicing.
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

.grid-list {
  &__items {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    margin-top: -3rem;
  }

  &__item {
    flex: 0 0 50%;
    padding: 3rem 1rem;
    display: flex;
  }

  &__number {
    font-size: $font-size-title;
    color: $color-primary;
    margin: 0 1rem;
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
    margin-bottom: 2rem;

    &--bold {
      font-weight: bold;
    }
  }

  &__list {
    list-style: disc;
    display: inline-block;
    list-style-position: inside;
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
