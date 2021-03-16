<template>
  <div class="services" id="services">
    <h3 class="global__section-title">Services</h3>
    <h1 class="global__title services__title">Choose the package that suits your needs</h1>
    <div class="services__cards">
      <div class="card">
        <div class="card__img">
          <img src="https://cdn.pixabay.com/photo/2013/10/09/02/27/lake-192990_960_720.jpg" alt="Small house over water" />
        </div>
        <div class="card__information">
          <h2 class="global__title--sub card__title">One page site</h2>
          <p class="global__paragraph card__paragraph">
            With his service I can build you a single webpage. It can be a standalone site or another page for a preexisting site.
          </p>
          <ul class="card__list">
            <li>Mobile Responsive</li>
            <li>Two free simple animations</li>
            <li>Takes one week</li>
          </ul>
          <h3 class="card__price">Starting at <span>£49.99</span></h3>
          <a href="" class="button card__button">Details</a>
        </div>
      </div>

      <div class="card">
        <div class="card__img">
          <img src="https://cdn.pixabay.com/photo/2016/06/24/10/47/house-1477041_960_720.jpg" alt="Modern house" />
        </div>
        <div class="card__information">
          <h2 class="global__title--sub card__title">Three page site</h2>
          <p class="global__paragraph card__paragraph">
            Our medium tier option gets you a multipage site with professional routing.
          </p>
          <ul class="card__list">
            <li>Mobile Responsive</li>
            <li>6 free simple animations</li>
            <li>Takes 4 weeks</li>
          </ul>
          <h3 class="card__price">Starting at <span>£149.99</span></h3>
          <a href="" class="button card__button">Details</a>
        </div>
      </div>

      <div class="card">
        <div class="card__img">
          <img src="https://cdn.pixabay.com/photo/2016/11/29/04/13/architecture-1867262_960_720.jpg" alt="Castle" />
        </div>
        <div class="card__information">
          <h2 class="global__title--sub card__title">Ten page website</h2>
          <p class="global__paragraph card__paragraph">
            The complete package.
          </p>
          <ul class="card__list">
            <li>Lorem, ipsum dolor.</li>
            <li>Lorem ipsum dolor sit.</li>
            <li>Takes at least 3 months</li>
          </ul>
          <h3 class="card__price">Starting at <span>£299.99+</span></h3>
          <a href="" class="button card__button">Details</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.services {
  margin: 13rem 0 0 0;
  display: flex;
  flex-direction: column;
  align-items: center;

  &__title {
    font-size: $font-size-title;
    margin-bottom: 6rem;
  }

  &__cards {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 2rem;

    & .card {
      // width: 33%;
      display: flex;
      flex-direction: column;
      align-items: center;
      border: 1px solid rgba(0, 0, 0, 0.089);
      border-radius: $border-radius-default;

      &:nth-child(2) {
        margin: 0 6rem;
      }

      &__img {
        width: 100%;
        height: 25rem;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: $border-radius-default $border-radius-default 0 0;

        & > img {
          width: 150%;
          height: auto;
        }
      }

      &__information {
        padding: 4rem 5rem;
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      &__title {
        font-size: $font-size-title--sub;
        // margin-bottom: 1.5rem;
      }

      &__paragraph {
        font-size: $font-size-text;
      }

      &__list {
        margin-bottom: 2.5rem;
        list-style-type: disc;
        & > li {
          font-size: $font-size-text;
        }
      }

      &__price {
        font-size: $font-size-text;

        & > span {
          color: $color-primary;
          font-weight: bold;
        }
      }

      &__button {
        position: relative;
        top: 7rem;
      }
    }
  }
}
</style>
