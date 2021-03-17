<template>
  <div class="contact" id="contact">
    <div class="contact__info">
      <h3 class="global__section-title">Contact</h3>
      <h1 class="global__title info__title">Get in touch</h1>
      <p class="global__paragraph info__paragraph">
        Send me a message with the form or say hi on one of my socials! If you have a project for me or want to talk tech don't hestitate to contact me :)
      </p>
      <h2 class="global__title--sub info__title--sub">Find me on social media!</h2>
      <div class="info__social-icons">
        <a href="https://github.com/Archf13nd" target="_blank" class="info__social-icon info__social-icon--github"></a>
        <a href="https://www.linkedin.com/in/alastair-parkyns-8a683a201/" target="_blank" class="info__social-icon info__social-icon--linked-in"></a>
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
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;

  &__info {
    flex: 0 0 min-content;
    padding: 2rem;
    max-width: 50%;
    min-width: 600px;
  }

  &__form {
    flex: 0 0 min-content;

    padding: 5rem;
    width: 100%;
    max-width: 50%;
    min-width: 600px;

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
    cursor: pointer;

    &--github {
      background: center / cover no-repeat url("../assets/icons/GitHub.png");
    }
    &--linked-in {
      background: center / cover no-repeat url("../assets/icons/LinkedIn.svg");
    }
  }
}
</style>
