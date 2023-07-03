<template>
  <aside class="result">
    <div class="result__header container">
      <logo color="var(--gray-4)"/>
      <div class="result__close" @click="$emit('close')" v-show="result && shakeEnd">
        <close/>
      </div>
    </div>
    <div class="result__wrap result-wait" v-show="!result || !shakeEnd">
<!--      <mini-elka/>-->
      <hands-elka/>
      <h1 class="result-wait__title">Трясём ёлочку…</h1>
    </div>
    <div class="result__wrap result-gift" v-show="result===1 && shakeEnd">
<!--      <gift/>-->
      <gift-success/>
      <div class="container">
        <h2 class="result-gift__title">Поздравляем, <br/> вы выиграли приз</h2>
        <p v-html="desc"/>
        <p v-show="big">Чтобы его получить, напишите в поддержку «Хочу подарок»</p>
        <a href="https://t.me/SamokatSupportBot" target="_blank" class="button" v-if="big">
          Написать в поддержку
        </a>
        <div class="button" @click="copy" v-else>
          {{ isCopied ? 'Скопировано' : 'Скопировать промокод' }}
        </div>
      </div>
    </div>
    <div class="result__wrap result-sorry" v-show="result===2 && shakeEnd">
<!--      <gift/>-->
      <gift-failure/>
      <div class="container">
        <h2 class="result-sorry__title">В этот раз <br/> удача вильнула хвостом</h2>
        <p>
          Но это не повод грустить! <br/>
          Лучше порадуйте себя любимыми продуктами из Самоката.
        </p>
        <a href="https://vml8.adj.st/promocategory/0ee772cf-ba70-49ce-9f8d-1c1c80f0b0ed?showStories&showcaseType=MINIMARKET&adj_t=347ewp7"
           target="_blank"
           class="button">
          Заказать в приложении
        </a>
      </div>
    </div>
  </aside>
</template>

<script>
import Logo from "@/components/logo";
import Close from "@/components/close";
import Gift from "@/components/gift";
import GiftSuccess from "@/components/gift-success";
import GiftFailure from "@/components/gift-failure";
export default {
  name: "result",
  components: {GiftFailure, GiftSuccess, Gift, Close, Logo},
  props: {
    code: String,
  },
  data: ()=>({
    result: 0,
    desc: 'Ваш подарок — Промокод <span>XXXX</span> на покупки в самокате на 1000 р.',
    big: false,
    shakeEnd: false,
    promoCode: '',
    isCopied: false
  }),
  methods: {
    sendCode() {
      this.$axios.$post(window.location.origin + '/query/', { code: this.code })
        .then(res => {
          if (res.promo) {
            if (res.promo.length < 20) {
              this.promoCode = res.promo
              this.desc = 'Ваш подарок — ' + res.desc.replace('XXXX', `<span>${res.promo}</span>`)
            } else {
              this.big = true
              this.desc = 'Ваш подарок — ' + res.desc
            }
            this.result = 1
          } else {
            this.result = 2
          }
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

    span {
      background: var(--coral);
      padding: 2px 8px;
      border-radius: 6px;
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
  &-sorry {
    //&__title {
    //  color: var(--green);
    //}
    //p { color: var(--gray); }
  }
}
</style>
