<template>
  <footer class="footer">
    <div class="container">
      <a href="https://vml8.adj.st/promocategory/0ee772cf-ba70-49ce-9f8d-1c1c80f0b0ed?showStories&showcaseType=MINIMARKET&adj_t=347ewp7"
         target="_blank" class="footer__app">
        <img src="/media/icon.svg" alt=""/>
        <span>Скачать приложение</span>
      </a>
      <small class="info">Сроки проведения акции: 06.07.2023 — 19.07.2023. Организатор ООО «Умный ритейл», ОГРН 1177847261602, 192019, Санкт-Петербург, ул.Седова, дом.11, Литер А, Этаж 6, помещение 627.</small>
      <div class="footer__copyright">
        <logo color="var(--white)"/>
        <small>2022 © ООО «Умный ритейл»</small>
      </div>
    </div>
  </footer>
</template>

<script>
import Logo from "@/components/logo";
export default {
  name: "footr",
  components: {Logo}
}
</script>

<style lang="scss">
.footer {
  &__app {
    display: inline-flex;
    align-items: center;
    padding: 12px 0;
    margin-bottom: 16px;
    img {
      width: 18px;
      height: 18px;
    }
    span {
      margin-left: 8px;
      font-size: 12px;
      color: var(--white);
    }
  }
  &__copyright {
    margin: 24px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    svg {
      height: 12px;
      width: auto;
    }
  }
}
</style>
