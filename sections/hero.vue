<template>
  <section class="hero">
    <div class="container">
      <a class="hero__logo" href="/">
        <logo/>
      </a>
      <h1 class="hero__title">Кино и призы</h1>
      <div class="hero__subtitle">
        Если новый эпизод сериала оказался скучным, поднять настроение поможет что-нибудь сладкое. Например, драже и мороженое.
      </div>
      <div class="hero__snikers">
        <img src="/media/snikers_m&m.png">
      </div>
      <div class="hero__subtitle">
        А если закажете их в приложении Самоката, то сможете выиграть классные призы.
      </div>
      <div class="button start">Ввести код и получить приз</div>
    </div>
  </section>
</template>

<script>
// import Logo from "@/components/logo";
export default {
  name: "hero",
  // components: {Logo}
}
</script>

<style lang="scss">
.hero {
  position: relative;
  &__logo {
    display: flex;
    margin: 28px 0 56px 0;
    height: 16px;
  }
  &__title {
    margin: 16px 0;
    color: var(--yellow);
    text-align: center;
  }
  &__snikers {
    margin: 18px 0;
    text-align: center;
  }
  &__subtitle {
    text-align: center;
  }
  .button {
    margin-top: 30px;
  }
}
</style>
