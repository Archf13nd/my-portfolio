<template>
  <div class="about" id="about">
    <div class="about__img">
      <img src="https://cdn.pixabay.com/photo/2016/07/02/12/21/eclipse-1492818_960_720.jpg" alt="Eclipse" />
    </div>
    <div class="about__info">
      <h3 class="global__section-title">About</h3>
      <h1 class="global__title info__title">I'm passionate about great websites</h1>
      <p class="global__paragraph info__paragraph">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias maiores, voluptates porro minima dolorum in Lorem ipsum dolor sit amet.
      </p>
      <ul class="info__list">
        <li>Lorem ipsum dolor sit amet consectetur adipisicing</li>
        <li>Lorem ipsum dolor sit amet consectetur adipisicing</li>
      </ul>
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

.info {
  &__title {
  }
  &__paragraph {
  }
  &__list {
    list-style-type: disc;
    list-style-position: inside;

    & > li {
      margin-top: 1rem;
    }
  }
}
</style>
