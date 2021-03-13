<template>
  <div class="intro" id="intro">
    <div class="intro__welcome">
      <div class="intro__introduction">
        <h3 class="global__section-title">Intro</h3>
        <div class="intro__title">
          Are you looking for a custom website that doesn't look like the rest?
          Look no futher!
        </div>
        <p class="intro__paragraph">
          I offer you my web tech skills so together we can build your dream
          website. Perhaps you got a design you want to see come to life? Or
          perhaps you have an idea or theme you want actualized and made to be?
          I'm the guy for you.
        </p>
        <p class="intro__paragraph">
          I take website building seriously. I say no to popular site builders
          like Wix and instead focus on a purer approach. I like optimization
          and creative freedom and I can't realize those two things with a
          website builder. If you like the same thing for your site then let's
          talk business
        </p>
      </div>
      <div class="intro__img">
        <img
          src="https://cdn.pixabay.com/photo/2018/06/09/17/25/avenue-3464777_960_720.jpg"
          alt="Path through twisted trees"
        />
      </div>
    </div>

    <div class="intro__production-stories">
      <div class="intro__production-story">
        <div class="intro__production-story__icon"></div>
        <h2 class="intro__production-story__title">Lorem ipsum dolor sit.</h2>
        <p class="intro__production-story__paragraph">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Molestiae
          exercitationem esse dolores accusantium vitae. Delectus architecto
          voluptate neque nobis optio ut officia explicabo perspiciatis in.
        </p>
      </div>
      <div class="intro__production-story">
        <div class="intro__production-story__icon"></div>
        <h2 class="intro__production-story__title">Lorem ipsum dolor sit.</h2>
        <p class="intro__production-story__paragraph">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Molestiae
          exercitationem esse dolores accusantium vitae. Delectus architecto
          voluptate neque nobis optio ut officia explicabo perspiciatis in.
        </p>
      </div>
      <div class="intro__production-story">
        <div class="intro__production-story__icon"></div>
        <h2 class="intro__production-story__title">Lorem ipsum dolor sit.</h2>
        <p class="intro__production-story__paragraph">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Molestiae
          exercitationem esse dolores accusantium vitae. Delectus architecto
          voluptate neque nobis optio ut officia explicabo perspiciatis in.
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.intro {
  position: relative;
  width: 100%;

  &__welcome {
    display: flex;
    align-items: center;
    justify-content: space-around;
    margin: 13rem 0;
    max-height: 70rem;
  }

  &__introduction {
    flex: 0 0 41.66%;
    padding: 4rem 6rem 0 0;
  }

  &__title {
    font-size: $font-size-title;
    font-weight: bold;
  }

  &__paragraph {
    font-size: $font-size-text;
  }

  &__img {
    flex: 0 0 58.33%;
    max-width: 50%;
    height: auto;

    & > img {
      width: 100%;
      height: auto;
      border-radius: 0.5rem;
    }
  }

  &__production-stories {
    display: flex;
    padding: 0 2rem;
  }

  &__production-story {
    width: 33.33%;

    &:nth-child(2) {
      margin: 0 6rem;
    }

    &__icon {
      width: 12rem;
      height: 12rem;
      background: #000;
    }

    &__title {
      font-size: $font-size-title--sub;
    }

    &__paragraph {
      font-size: $font-size-text;
    }
  }
}
</style>
