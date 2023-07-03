<template>
  <section class="form">
    <div class="container">
      <h2 class="form__title">Чтобы получить приз, введите код из СМС</h2>
      <label>
        <input type="text" class="input" ref="code" v-model="code" placeholder="Введите код из смс"/>
      </label>
      <div class="button" @click="validate">Получить приз</div>
    </div>
    <result v-if="resultView" :code="code" @close="resultView=false"/>
  </section>
</template>

<script>
import Result from "@/sections/result";
export default {
  name: "promo",
  components: {Result},
  data: ()=>({
    code: '',
    resultView: false,
  }),
  methods: {
    validate() {
      if (this.code) {
        this.resultView = true
      } else {
        this.$refs.code.classList.add('danger')
        setTimeout(()=>{
          this.$refs.code.classList.remove('danger')
        }, 2000)
      }
    }
  }
}
</script>

<style lang="scss">
.form {
  position: relative;
  z-index: 1;
  &__title {
    text-align: center;
    color: var(--yellow);
    margin-top: 42px;
    margin-bottom: 32px;
  }
  .button { margin: 0 auto; }
  .input { margin-bottom: 12px; }
}
</style>
