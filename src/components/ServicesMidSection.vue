<template>
  <div class="services-mid-section">
    <div class="services-mid-section__img">
      <img
        src="https://cdn.pixabay.com/photo/2017/02/08/12/46/moon-2048727_960_720.jpg"
        alt="Moon"
      />
    </div>
    <div class="services-mid-section__info services-mid-section__info--left">
      <div class="info-points">
        <h2 class="info-points__title">Be visible on the internet</h2>
        <div class="info-points__point">
          <h2 class="info-points__title-sub" id="1" @click="showParagraph">
            Lorem ipsum dolor sit amet
          </h2>
          <transition
            :css="false"
            @before-enter="beforeEnter"
            @enter="enter"
            @leave="leave"
            @after-enter="afterEnter"
            @before-leave="beforeLeave"
            @enter-cancelled="enterCancelled"
            @leave-cancelled="leaveCancelled"
          >
            <div class="info-points__paragraph" v-if="activeParagraph === '1'">
              <p class="info-points__paragraph-text">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quod
                consequuntur delectus, voluptate corporis temporibus cum.
                Corporis fuga placeat libero iste tempore.
              </p>
            </div>
          </transition>
        </div>
        <div class="info-points__point">
          <h2 class="info-points__title-sub" id="2" @click="showParagraph">
            Lorem ipsum dolor sit amet
          </h2>
          <transition
            :css="false"
            @before-enter="beforeEnter"
            @enter="enter"
            @leave="leave"
            @after-enter="afterEnter"
            @before-leave="beforeLeave"
            @enter-cancelled="enterCancelled"
            @leave-cancelled="leaveCancelled"
          >
            <div class="info-points__paragraph" v-if="activeParagraph === '2'">
              <p class="info-points__paragraph-text">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quod
                consequuntur delectus, voluptate corporis temporibus cum.
                Corporis fuga placeat libero iste tempore.
              </p>
            </div>
          </transition>
        </div>
        <div class="info-points__point">
          <h2 class="info-points__title-sub" id="3" @click="showParagraph">
            Lorem ipsum dolor sit amet
          </h2>
          <transition
            :css="false"
            @before-enter="beforeEnter"
            @enter="enter"
            @leave="leave"
            @after-enter="afterEnter"
            @before-leave="beforeLeave"
            @enter-cancelled="enterCancelled"
            @leave-cancelled="leaveCancelled"
          >
            <div class="info-points__paragraph" v-if="activeParagraph === '3'">
              <p class="info-points__paragraph-text">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quod
                consequuntur delectus, voluptate corporis temporibus cum.
                Corporis fuga placeat libero iste tempore.
              </p>
            </div>
          </transition>
        </div>
      </div>
    </div>
    <div
      class="services-mid-section__info services-mid-section__info--right"
    ></div>
    <div class="services-mid-section__img">
      <img
        src="https://cdn.pixabay.com/photo/2011/12/14/12/21/orion-nebula-11107_960_720.jpg"
        alt="Universe"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sectionOneParagraph: "1",
      sectionTwoParagraph: "1",
      slideDownInInterval: null,
      slideDownOutInterval: null,
    };
  },
  methods: {
    beforeEnter(e) {
      console.log("Before enter", e.getBoundingClientRect());
    },
    enter(e, done) {
      const maxHeight = e.firstChild.getBoundingClientRect().height;
      let currentHeight = 0;
      function animate() {
        if (currentHeight >= 100) {
          done();
          console.log(e.style.height);
          return;
        }
        e.style.height = `${(maxHeight / 100) * (currentHeight += 5)}px`;
        requestAnimationFrame(animate);
      }
      requestAnimationFrame(animate);
    },
    afterEnter() {
      console.log("After enter");
    },
    beforeLeave() {
      console.log("Before leave");
    },
    leave(e, done) {
      const maxHeight = e.firstChild.getBoundingClientRect().height;
      let currentHeight = 100;
      function animate() {
        if (currentHeight <= 1) {
          done();
          console.log(e.style.height);

          return;
        }
        e.style.height = `${(maxHeight / 100) * (currentHeight -= 5)}px`;
        requestAnimationFrame(animate);
      }

      requestAnimationFrame(animate);
    },
    afterLeave() {
      console.log("After leave");
    },
    enterCancelled() {
      clearInterval(this.slideDownInInterval);
    },
    leaveCancelled() {
      clearInterval(this.slideDownOutInterval);
    },
    showParagraph(e) {
      console.log(e.target.id);
      this.sectionOneParagraph = e.target.id;
    },
  },
  computed: {
    activeParagraph() {
      return this.sectionOneParagraph;
    },
  },
};
</script>

<style lang="scss" scoped>
.services-mid-section {
  min-height: 100vh;
  margin-top: 13rem;
  display: grid;
  align-items: center;
  grid: repeat(2, calc(1080px / 2)) / repeat(2, calc(1920px / 2));

  &__img {
    height: 100%;
    width: 100%;
    overflow: hidden;

    & > img {
      width: 100%;
      height: auto;
    }
  }

  &__info {
    width: 100%;
    max-width: 45%;
    margin: 10rem;

    &--left {
      justify-self: start;
    }

    &--right {
      justify-self: end;
    }
  }
}

.info-points {
  &__point {
    position: relative;
    width: 100%;
    height: min-content;
    margin-bottom: 4rem;
  }

  &__title {
    font-size: $font-size-title;
    font-weight: bold;
    margin-bottom: 3rem;
  }

  &__title-sub {
    font-size: $font-size-title--sub;
    font-weight: bold;
    transition: all 0.1s ease-in;
    // margin-bottom: 1.5rem;
    cursor: pointer;

    &:hover {
      color: $color-primary;
    }
  }

  &__paragraph {
    width: 100%;
    overflow: hidden;
    // background: #000;

    margin-bottom: 2rem;
    // transform: translateY(-19px);
  }
  &__paragraph-text {
    padding-top: 1.5rem;
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
