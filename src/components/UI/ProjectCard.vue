<template>
  <div class="projectCard">
    <div
      class="projectCard__img"
      :style="{
        background: `no-repeat center / cover content-box url('https://cdn.pixabay.com/photo/2011/12/14/12/21/orion-nebula-11107_960_720.jpg')`
      }"
    ></div>
    <div class="projectCard__info">
      <h2 class="global__title--sub projectCard__title">{{ title }}</h2>
      <h3 class="projectCard__title--sub">{{ titleSub }}</h3>
      <p class="projectCard__paragraph">
        {{ paragraphOne }}
      </p>
      <p class="projectCard__paragraph">
        {{ paragraphTwo }}
      </p>
      <p class="projectCard__paragraph projectCard__paragraph--quote">
        <em>{{ paragraphQuote }}</em>
      </p>
      <div class="projectCard__buttons">
        <div class="button projectCard__buttons__button" @click="backButtonClicked">
          Back
        </div>
        <a href="https://conclave-messaging.netlify.app/" target="_blank" class="button projectCard__buttons__button">
          Visit
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["img", "title", "titleSub", "paragraphOne", "paragraphTwo", "paragraphQuote"],
  methods: {
    backButtonClicked() {
      this.$emit("close");
    }
  }
};
</script>

<style lang="scss" scoped>
.projectCard {
  position: relative;
  display: flex;
  background: #fff;
  font-size: $font-size-text;
  //   z-index: 10;

  &__img {
    flex: 0 0 70%;
    height: 100%;
    border: 2rem solid #fff;
  }

  &__info {
    padding: 5rem;
    background: #fff;
  }

  &__title {
    &--sub {
      font-size: $font-size-text;
      margin-top: 2rem;
    }
  }

  &__paragraph {
    margin-top: 2rem;

    &--quote {
      padding: 2rem;
    }
  }

  &__buttons {
    position: absolute;
    bottom: 4rem;
    display: flex;

    &__button {
      margin-right: 2rem;
      font-size: $font-size-text;
    }
  }
}
</style>
