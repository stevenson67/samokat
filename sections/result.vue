<template>
  <aside class="result">
    <div class="result__header container">
      <logo color="var(--white)"/>
      <div class="result__close" @click="$emit('close')" v-show="result && shakeEnd">
        <close/>
      </div>
    </div>
    <div class="result__wrap result-wait" v-show="!result || !shakeEnd">
<!--      <mini-elka/>-->
      <mini-popcorn/>
      <h1 class="result-wait__title">Свет, камера…</h1>
    </div>
    <div class="result__wrap result-certificate" v-show="result==='FASTCODE' && shakeEnd">
      <!--      <gift/>-->
      <gift-success/>
      <div class="container">
        <h2 class="result-gift__title">Свет, камера, приз!</h2>
        <p>
          Поздравляем, вы выиграли сертификат <span>{{ promoCode }}</span> <br/>
          на покупки в Самокате на 1 000 ₽.
          Можно заказать сладости и попробовать выиграть что-то ещё — наушники, колонку или кинопроектор.
        </p>
        <div class="button" @click="copy">
          {{ isCopied ? 'Скопировано' : 'Скопировать промокод' }}
        </div>
      </div>
    </div>
    <div class="result__wrap result-certificate" v-show="result==='10000' && shakeEnd">
      <!--      <gift/>-->
      <gift-success/>
      <div class="container">
        <h2 class="result-gift__title">Свет, камера, приз!</h2>
        <p>
          Поздравляем, вы выиграли сертификат <br>на 10 000 ₽ на наушники или колонку. <br>Теперь звук будет объёмным и глубоким, <br>как в кинотеатре.
        </p>
        <h3 class="result-gift__title">Чтобы получить сертификат, <br>отправьте свои данные на почту <a class="result__wrap-mail">data@gp-g.ru</a></h3>
        <p>
          — имя и фамилия;<br>
          — электронный адрес и номер телефона;<br>
          — сканы страниц паспорта<br>(разворот и прописка);<br>
          — скан свидетельства ИНН;<br>
          — адрес, куда доставить приз.
        </p>
        <a href="https://t.me/SamokatSupportBot" target="_blank" class="button">
          Написать в поддержку
        </a>
      </div>
    </div>
    <div class="result__wrap result-certificate" v-show="result==='30000' && shakeEnd">
      <!--      <gift/>-->
      <gift-success/>
      <div class="container">
        <h2 class="result-gift__title">Свет, камера, приз!</h2>
        <p>
          Поздравляем, вы выиграли <br>
          кинопроектор. Теперь смотреть фильмы <br>
          будет комфортнее и атмосфернее.
        </p>
        <h3 class="result-gift__title">Чтобы получить сертификат, <br>отправьте свои данные на почту <a class="result__wrap-mail">data@gp-g.ru</a></h3>
        <p>
          — имя и фамилия;<br>
          — электронный адрес и номер телефона;<br>
          — сканы страниц паспорта<br>(разворот и прописка);<br>
          — скан свидетельства ИНН;<br>
          — адрес, куда доставить приз.
        </p>
        <a href="https://t.me/SamokatSupportBot" target="_blank" class="button">
          Написать в поддержку
        </a>
      </div>
    </div>
    <div class="result__wrap result-sorry" v-show="result==='nothing' && shakeEnd">
      <!--      <gift/>-->
      <gift-success/>
      <div class="container">
        <h2 class="result-sorry__title">Свет, камера, приз!</h2>
        <p>
          К сожалению, вы ничего не выиграли, но можно попробовать снова. Помните, что некоторые актёры получили «Оскар» с шестой попытки.
        </p>
        <a href="https://t.me/SamokatSupportBot" target="_blank" class="button">
          Написать в поддержку
        </a>
      </div>
    </div>
  </aside>
</template>

<script>
import Logo from "@/components/logo";
import Close from "@/components/close";
import GiftSuccess from "@/components/gift-success";
export default {
  name: "result",
  components: {GiftSuccess, Close, Logo},
  props: {
    code: String,
  },
  data: ()=>({
    result: 0,
    big: false,
    shakeEnd: false,
    promoCode: '',
    isCopied: false
  }),
  methods: {
    sendCode() {
      this.$axios.$post( 'https://kinoprizy.samokat.ru' + '/query/', { code: this.code })
        .then(res => {
          if (res.promo)
            switch ( res.promo ) {
              case "":
                this.result = "nothing"
                break
              case "10000":
                this.result = "10000"
                break
              case "30000":
                this.result = "30000"
                break
              default:
                this.result = "FASTCODE"
                break
            }
          else
            this.result = "nothing"
          this.promoCode = res.promo
        })
    },
    copy() {
      navigator.clipboard.writeText(this.promoCode)
      this.isCopied= true
      setTimeout(()=>{
        this.isCopied = false
      }, 1000)
    }
  },
  mounted() {
    this.sendCode()
    document.body.style.overflow = 'hidden'
    setTimeout(()=>{
      this.shakeEnd = true
    }, 3000)
  },
  destroyed() {
    document.body.style.overflow = ''
  }
}
</script>

<style lang="scss">
.result {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  z-index: 999;
  background: var(--green);
  display: flex;
  flex-direction: column;
  text-align: center;

  &.sorry { background: var(--lime); }

  &__header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 28px;
    margin-top: 24px;
  }
  &__close {
    display: flex;
    cursor: pointer;
  }
  &__wrap {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    padding-top: 15%;
    &-mail {
      color: var(--coral);
      text-decoration: underline;
    }
    span {
      background: var(--coral);
      padding: 2px 8px;
      border-radius: 6px;
      line-height: 3em;
    }
    .button {
      border-radius: 0;
      position: absolute;
      left: 0; bottom: 0;
      width: 100%;
      max-width: unset;
    }
  }
  &-wait {
    &__title {
      color: var(--lime);
      margin-top: 40px;
    }
  }
  &-gift, &-sorry {
    &__title {
      color: var(--yellow);
    }
    p { color: var(--gray-4); }
  }
}
@media (max-height: 600px) {
  .result__wrap .container h2 {
    margin: 0;
  }
  .result__wrap .container p {
    margin: 5px 0;
  }
  .result__wrap .container h3 {
    margin: 10px 0 5px 0;
  }
}
</style>
