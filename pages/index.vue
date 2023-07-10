<template>
  <main className="main">
    <cookies/>
    <hero/>
    <orders/>
    <certificates/>
    <promo/>
    <apps/>
    <footr/>
  </main>
</template>

<script>
import Hero from "~/sections/hero";
import Promo from "@/sections/promo";
import Apps from "@/sections/apps";
import Footr from "@/sections/footr";
import Cookies from "@/components/cookies";

export default {
  components: {Cookies, Footr, Apps, Promo, Hero},
  methods: {
    scrollToForm() {
      let form = document.querySelector('.form')
      window.scroll({
        behavior: 'smooth', left: 0,
        top: form.offsetTop - window.innerHeight / 4
      });
    }
  },
  mounted() {
    document.addEventListener('scroll', function () {
      let offset = window.scrollY - window.innerHeight / 100
      let offsetPopcorn = window.scrollY - window.innerHeight - 300

      document.querySelectorAll('.corn-1').forEach(item => {
        item.style = `transform: translateY(${offset / 20}px)`
      })
      document.querySelectorAll('.corn-2').forEach(item => {
        item.style = `transform: translateY(${offset / 10}px)`
      })
      document.querySelectorAll('.corn-3').forEach(item => {
        item.style = `transform: translateY(${offset / 5}px)`
      })
      document.querySelectorAll('.snikers').forEach(item => {
        item.style = `transform: translateY(${offset / 8}px)`
      })
      document.querySelectorAll('.scroll-1').forEach(item => {
        item.style = `transform: translateY(${offsetPopcorn / 20}px)`
      })
      document.querySelectorAll('.scroll-2').forEach(item => {
        item.style = `transform: translateY(${offsetPopcorn / 10}px)`
      })
      document.querySelectorAll('.scroll-3').forEach(item => {
        item.style = `transform: translateY(${offsetPopcorn / 30}px)`
      })
      document.querySelectorAll('.m_m').forEach(item => {
        item.style = `transform: rotate(-${offset / 180}deg)`
      })
      document.querySelectorAll('svg path.scroll-hi').forEach(item => {
        item.style = `transform: rotate(-${offset / 20}deg)`
      })

      document.querySelectorAll('svg path.scroll-light').forEach(item => {
        let bound = item.getBoundingClientRect()
        if (bound.top < window.innerHeight / 1.75)
          item.classList.add('active')
        else
          item.classList.remove('active')
      })
    })

    document.querySelectorAll('.button.start').forEach(item => {
      item.addEventListener('click', this.scrollToForm)
      item.addEventListener('touchend', this.scrollToForm)
    })
  }
}
</script>
