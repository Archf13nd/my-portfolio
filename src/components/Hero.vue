<template>
  <div ref="hero" id="hero" class="hero">
    <h1 class="hero__title">Conclave Web Services</h1>
    <p class="hero__paragraph">
      I develop websites of all kinds. Have a design? For a price I'll make it sublime
    </p>
    <a class="button button--hero" href="#intro">I'm interested</a>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  mounted() {
    this.$emit("heroRef", this.$refs.hero);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.hero {
  width: 100vw;
  height: 85vh;
  background: #000;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  &__title {
    font-size: 10rem;
    color: white;
    text-align: center;
  }

  &__paragraph {
    color: white;
    font-size: 3.33rem;
    text-align: center;
  }
}

.button--hero {
  margin: 3rem auto;
}
</style>
