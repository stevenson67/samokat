<template>
  <div class="cookies" v-if="show">
    <span>
      Продолжая использовать сайт,
      Вы соглашаетесь со сбором файлов cookie для корректного функционирования сайта в соответствии с
      <a href="https://samokat.ru/smart-space/privacy/" target="_blank">Политикой Конфиденциальности</a>.
    </span>
    <div class="button" @click="accept">Ок</div>
  </div>
</template>

<script>
export default {
  name: "cookies",
  data: ()=>({
    show: false
  }),
  methods: {
    accept() {
      localStorage.setItem('cookieAccept', 'true')
      this.show = false
    }
  },
  mounted() {
    if (!localStorage.getItem('cookieAccept') || localStorage.getItem('cookieAccept') === 'false') {
      localStorage.setItem('cookieAccept', 'false')
      this.show = true
    }
  }
}
</script>

<style lang="scss">
.cookies {
  position: fixed;
  width: calc(100% - 16px);
  bottom: 8px;
  right: 8px;
  display: flex;
  flex-direction: column;
  height: auto;
  padding: 16px;
  background-color: #fff;
  border-radius: 16px;
  box-shadow: 0 2px 16px 0 rgba(0,0,0, .2);
  z-index: 1000;

  span {
    font-size: 13px;
    line-height: 120%;
    margin: 0 0 16px 0;
    text-align: center;
  }
  a {
    color: var(--coral);
    &:hover { text-decoration: underline; }
  }
  .button {
    border-radius: 10px;
    padding: 16px;
    transition: .2s ease-in-out;

    &:hover {
      box-shadow: none;
      transform: scale(1.05);
    }
  }
}
</style>
