<template>
  <div class="about" id="about">
    <div class="about__img">
      <img src="https://cdn.pixabay.com/photo/2016/07/02/12/21/eclipse-1492818_960_720.jpg" alt="Eclipse" />
    </div>
    <div class="about__info">
      <h3 class="global__section-title">About</h3>
      <h1 class="global__title info__title">Hey, I'm Alastair</h1>
      <p class="global__paragraph info__paragraph">
        I've always loved technology and working out how things work. For the last few years my focus has been on the web and I never fail to find something new
        or cool to try out or mess with.
      </p>
      <p class="global__paragraph info__paragraph">
        The internet is growing faster than ever and new technologies solving many many different problems or introducing many new and exciting features are
        appearing week after week. I have a passion to learn and a drive to build and I'm always exicted to see what I can create next.
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.about {
  width: 100%;
  height: 100%;
  margin-top: 13rem;
  display: flex;
  align-items: center;
  font-size: $font-size-text;
  &__img {
    flex: 0 0 60%;
    // width: 50%;
    height: auto;
    padding: 5rem;
  }

  &__info {
    padding: 4rem;
  }
}
</style>
