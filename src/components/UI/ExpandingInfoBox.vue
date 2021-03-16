<template>
  <div class="info-points">
    <h2 class="global__title info-points__title">What my services include:</h2>
    <div class="info-points__points">
      <div class="info-points__point">
        <h2
          class="info-points__number"
          :class="{
            'info-points__number--active': activeParagraph === '1'
          }"
        >
          1
        </h2>
        <div class="info-points__text">
          <h2 class="global__title--sub info-points__title-sub" id="1" @click="showParagraph">
            Mobile Responsiveness
          </h2>
          <transition :css="false" @enter="enter" @leave="leave" @enter-cancelled="enterCancelled" @leave-cancelled="leaveCancelled">
            <div class="info-points__paragraph" v-if="activeParagraph === '1'">
              <p class="global__paragraph info-points__paragraph-text">
                In today's world it's more important than ever to make the web accessible to mobile users. Because of this I make every site I build mobile
                responsive.
              </p>
            </div>
          </transition>
        </div>
      </div>
      <div class="info-points__point">
        <h2
          class="info-points__number"
          :class="{
            'info-points__number--active': activeParagraph === '2'
          }"
        >
          2
        </h2>
        <div class="info-points__text">
          <h2 class="global__title--sub info-points__title-sub" id="2" @click="showParagraph">
            Speed
          </h2>
          <transition :css="false" @enter="enter" @leave="leave" @enter-cancelled="enterCancelled" @leave-cancelled="leaveCancelled">
            <div class="info-points__paragraph" v-if="activeParagraph === '2'">
              <p class="global__paragraph info-points__paragraph-text">
                Your users are likely to click off your site if it's too slow. I always consider performance and employ a selection of advanced techniques to
                give your site the speed it needs.
              </p>
            </div>
          </transition>
        </div>
      </div>
      <div class="info-points__point">
        <h2
          class="info-points__number"
          :class="{
            'info-points__number--active': activeParagraph === '3'
          }"
        >
          3
        </h2>
        <div class="info-points__text">
          <h2 class="global__title--sub info-points__title-sub" id="3" @click="showParagraph">
            SEO - Discoverable
          </h2>
          <transition :css="false" @enter="enter" @leave="leave" @enter-cancelled="enterCancelled" @leave-cancelled="leaveCancelled">
            <div class="global__paragraph info-points__paragraph" v-if="activeParagraph === '3'">
              <p class="global__paragraph info-points__paragraph-text">
                You may have heard SEO being thrown around. It's an important aspect of a website and one I don't skip. By using a selection of techniques I
                will give your site the best chance it can get at reaching the top of the search results
              </p>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentParagraph: "1",
      preventClick: false
    };
  },
  methods: {
    enter(e, done) {
      this.preventClick = true;

      const maxHeight = e.firstChild.getBoundingClientRect().height;
      // const maxHeight = 100;
      e.style.height = 0;

      let startTime;
      const animate = time => {
        if (!startTime) {
          startTime = time;
        }
        const elapsed = time - startTime;

        const heightVal = Math.min((maxHeight / 100) * Math.min(0.3 * elapsed, 100));
        e.style.height = heightVal + "px";
        if (heightVal >= maxHeight) {
          this.preventClick = false;
          done();

          return;
        } else {
          requestAnimationFrame(animate);
        }
      };
      requestAnimationFrame(animate);
    },
    leave(e, done) {
      this.preventClick = true;
      const maxHeight = e.firstChild.getBoundingClientRect().height;
      // const maxHeight = 100;

      let startTime;
      const animate = time => {
        if (!startTime) {
          startTime = time;
        }
        const elapsed = time - startTime;

        const heightVal = Math.min(maxHeight - (maxHeight / 100) * Math.max(0.3 * elapsed, 0));
        e.style.height = heightVal + "px";
        if (heightVal <= 0) {
          this.preventClick = false;
          done();
          return;
        } else {
          requestAnimationFrame(animate);
        }
      };
      requestAnimationFrame(animate);
    },
    enterCancelled() {
      clearInterval(this.slideDownInInterval);
    },
    leaveCancelled() {
      clearInterval(this.slideDownOutInterval);
    },
    showParagraph(e) {
      if (this.preventClick) {
        return;
      }
      this.currentParagraph = e.target.id;
    }
  },
  computed: {
    activeParagraph() {
      return this.currentParagraph;
    }
  }
};
</script>

<style lang="scss" scoped>
.info-points {
  &__points {
    margin-top: 3rem;
    height: 100%;
  }
  &__point {
    position: relative;
    width: 100%;
    height: min-content;
    margin-bottom: 2rem;
    display: flex;
  }

  &__title {
    font-size: $font-size-title;
    font-weight: bold;
  }

  &__text {
    min-height: 5rem;
    margin: 0;
  }

  &__title-sub {
    font-weight: bold;
    transition: all 0.1s ease-in;
    display: flex;
    align-items: center;
    cursor: pointer;

    &:hover {
      color: $color-primary;
    }
    &:hover > span {
      background: $color-primary;
      color: $color-white;
    }
  }

  &__number {
    position: relative;
    top: -6px;
    flex: 0 0 5rem;
    display: flex;
    height: 5rem;
    justify-content: center;
    align-items: center;
    border: 3px solid $color-primary;
    border-radius: 50%;
    margin-right: 2rem;
    transition: all 0.1s ease-in;
    font-size: $font-size-title--sub;

    &--active {
      background: $color-primary;
      color: $color-white;
    }
  }

  &__paragraph {
    width: 100%;
    overflow: hidden;
    // background: #000;
  }
  &__paragraph-text {
    // padding-top: 1.5rem;
    font-size: $font-size-text;
  }
}

.slide-down-enter-active {
  animation: slideDown 0.3s ease-in forwards;
}
.slide-down-leave-active {
  animation: slideDown 0.3s ease-in backwards;
}
</style>
