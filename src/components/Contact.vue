<template>
  <div class="contact" id="contact">
    <div class="contact__info">
      <h3 class="global__section-title">Contact</h3>
      <h1 class="global__title info__title">Get in touch</h1>
      <p class="global__paragraph info__paragraph">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta, ullam perspiciatis itaque quaerat aliquid velit nulla. Quo provident iure tempora!
      </p>
      <h2 class="global__title--sub info__title--sub">Find me on social media!</h2>
      <div class="info__social-icons">
        <div class="info__social-icon"></div>
        <div class="info__social-icon"></div>
        <div class="info__social-icon"></div>
      </div>
    </div>
    <form class="contact__form">
      <input type="text" placeholder="Name" />
      <input type="email" placeholder="Email" />
      <textarea rows="10" cols="33" placeholder="Type me a message"></textarea>
      <input type="submit" value="Submit Message" />
    </form>
  </div>
</template>

<style lang="scss" scoped>
.contact {
  margin-top: 13rem;
  display: flex;
  align-items: center;

  &__info {
    flex: 0 0 50%;
    padding: 2rem;
  }

  &__form {
    padding: 5rem;
    width: 100%;
    display: flex;
    flex-direction: column;
  }
}

input,
textarea {
  padding: 0 2rem;
  margin-top: 3rem;
  width: 100%;
}

textarea {
  padding-top: 2rem;
}

input {
  height: 5rem;
}

.info {
  // &__title {
  //   &--sub {
  //   }
  // }

  // &__paragraph {
  // }

  &__social-icons {
    display: flex;
  }

  &__social-icon {
    margin-right: 3rem;
    width: 50px;
    height: 50px;
    background: #000;
  }
}
</style>
