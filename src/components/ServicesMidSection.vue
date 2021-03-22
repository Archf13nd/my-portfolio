<template>
  <div class="services-mid-section">
    <div class="services-mid-section__img">
      <img src="https://cdn.pixabay.com/photo/2017/02/08/12/46/moon-2048727_960_720.jpg" alt="Moon" />
    </div>
    <expanding-info-box class="services-mid-section__info services-mid-section__info--left"></expanding-info-box>

    <business-stat-nav-box class="services-mid-section__info services-mid-section__info--right"></business-stat-nav-box>

    <div class="services-mid-section__img">
      <img src="https://cdn.pixabay.com/photo/2011/12/14/12/21/orion-nebula-11107_960_720.jpg" alt="Universe" />
    </div>
  </div>
</template>

<script>
import ExpandingInfoBox from "./UI/ExpandingInfoBox.vue";
import BusinessStatNavBox from "./UI/BusinessStatNavBox.vue";
export default {
  components: { ExpandingInfoBox, BusinessStatNavBox },
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
.services-mid-section {
  min-height: 100vh;
  margin-top: 13rem;
  display: grid;
  align-items: center;
  grid-template-columns: repeat(auto-fill, minmax(700px, 1fr));
  grid-template-rows: 1fr 1fr;

  &__img {
    overflow: hidden;
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-items: center;

    &:first-child {
      // align-items: flex-end;
    }

    & > img {
      width: 100%;
      height: auto;
    }
  }

  &__info {
    width: 100%;
    max-width: 45%;
    height: 60%;
    margin: 10rem 15rem;

    &--left {
      justify-self: start;

      @media screen and (max-width: 1200px) {
        justify-self: center;
      }
    }

    &--right {
      justify-self: end;
      @media screen and (max-width: 1200px) {
        justify-self: center;
        max-width: 60%;
      }
    }
  }
}
</style>
