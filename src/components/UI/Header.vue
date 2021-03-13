<template>
  <header class="header" :class="{ 'header__screen-top': !adjustNav }">
    <div class="logo">Logo</div>
    <ul class="header__nav-items">
      <li class="header__nav-items__item">
        <a href="#hero" class="header__nav-items__item-link">Home</a>
      </li>
      <li class="header__nav-items__item">
        <a href="#intro" class="header__nav-items__item-link">Intro</a>
      </li>
      <li class="header__nav-items__item">
        <a href="#services" class="header__nav-items__item-link">Services</a>
      </li>
      <li class="header__nav-items__item">
        <a class="header__nav-items__item-link">Projects</a>
      </li>
      <li class="header__nav-items__item">
        <a class="header__nav-items__item-link">About</a>
      </li>
      <li class="header__nav-items__item">
        <a class="header__nav-items__item-link">Contact</a>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  props: ["adjustNav"],
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.header {
  position: fixed;
  z-index: 100;
  top: 0;

  width: 100%;
  height: 8rem;
  background: $color-primary;
  display: flex;
  justify-content: space-around;
  align-items: center;

  transition: all 0.3s ease-in; //todo Create animation

  &__nav-items {
    display: flex;
    font-size: 2rem;
    font-weight: bold;
    color: $color-white;
    &__item {
      padding: 4px 12px;
      cursor: pointer;
      transition: all 0.15s linear;

      &:hover {
        color: $color-white;
      }
    }
  }
}

.header__screen-top {
  height: 12rem;
  background: transparent;
  color: $color-white;
  & .header__nav-items__item:hover {
    color: $color-primary;
  }
}
</style>
