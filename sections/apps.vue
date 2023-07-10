<template>
  <section class="apps">
    <div class="container">
      <div class="apps__ice">
        <img class="ice" src="/media/ice_cream.svg">
        <svg class="star" width="48" height="60" viewBox="0 0 48 60" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M19.5346 21.3701C15.6986 27.2026 5.53997 30.2691 0.940171 31.0733C16.5668 29.74 22.1901 49.1987 23.0484 59.0947C24.8483 36.5676 40.0607 30.8525 47.442 30.8109C31.3869 28.7224 25.5735 9.53281 24.6737 0.199056C24.559 4.82588 23.3707 15.5377 19.5346 21.3701Z" fill="white"/>
        </svg>
        <svg class="disc-1" width="12" height="13" viewBox="0 0 12 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 7.11768C12 10.4314 9.31371 12.6177 6 12.6177C2.68629 12.6177 0 9.93138 0 6.61768C0 3.30397 2.68629 0.617676 6 0.617676C9.31371 0.617676 12 3.80397 12 7.11768Z" fill="#97C2D1"/>
        </svg>
        <svg class="disc-2" width="12" height="13" viewBox="0 0 12 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 6.85986C12 10.1736 9.31371 12.3599 6 12.3599C2.68629 12.3599 0 9.67357 0 6.35986C0 3.04615 2.68629 0.359863 6 0.359863C9.31371 0.359863 12 3.54615 12 6.85986Z" fill="#4CA859"/>
        </svg>
        <svg class="disc-3" width="21" height="20" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M6.70796 19.1987C1.46153 17.6431 -0.738883 12.3637 0.81669 7.11726C2.37226 1.87083 7.88638 -1.12121 13.1328 0.434363C18.3792 1.98994 21.3713 7.50405 19.8157 12.7505C18.2601 17.9969 11.9544 20.7542 6.70796 19.1987Z" fill="#D3360E"/>
        </svg>
        <svg class="disc-4" width="12" height="13" viewBox="0 0 12 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 7.11768C12 10.4314 9.31371 12.6177 6 12.6177C2.68629 12.6177 0 9.93138 0 6.61768C0 3.30397 2.68629 0.617676 6 0.617676C9.31371 0.617676 12 3.80397 12 7.11768Z" fill="#97C2D1"/>
        </svg>
        <svg class="disc-5" width="21" height="20" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M6.70796 19.1987C1.46153 17.6431 -0.738883 12.3637 0.81669 7.11726C2.37226 1.87083 7.88638 -1.12121 13.1328 0.434363C18.3792 1.98994 21.3713 7.50405 19.8157 12.7505C18.2601 17.9969 11.9544 20.7542 6.70796 19.1987Z" fill="#E1A49E"/>
        </svg>
        <svg class="sticks-1" width="35" height="33" viewBox="0 0 35 33" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path class="sticks-anim" d="M26.955 5.40021C22.218 11.5844 18.6791 18.7588 15.6442 25.9078C15.626 25.9506 15.0026 27.6067 14.7917 29.2302" stroke="white" stroke-width="2"/>
          <path class="sticks-anim" d="M13.1078 9.7998C9.89048 14.167 6.87899 20.0565 6.39458 25.5522" stroke="white" stroke-width="2"/>
        </svg>
        <svg class="sticks-2" width="19" height="33" viewBox="0 0 19 33" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path class="sticks-anim" d="M13.812 2.23686C11.3839 9.6388 7.46206 16.6112 3.27658 23.1534C3.25149 23.1926 2.23695 24.6424 1.01621 25.7333" stroke="white" stroke-width="2"/>
          <path class="sticks-anim" d="M18.002 16.1489C16.2152 21.2705 13.0558 27.082 8.79409 30.5857" stroke="white" stroke-width="2"/>
        </svg>
      </div>
      <h2 class="apps__title">Впереди много кинопремьер</h2>
      <span>А это значит, что можно перейти в приложение Самоката, заказать сладости и попробовать выиграть ещё один приз. Продолжение следует!</span>
      <a href="https://vml8.adj.st/promocategory/0ee772cf-ba70-49ce-9f8d-1c1c80f0b0ed?showStories&showcaseType=MINIMARKET&adj_t=347ewp7"
         target="_blank" class="button">
        Перейти в приложение
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: "apps"
}
</script>

<style lang="scss">
.apps {
  margin-top: 64px;
  margin-bottom: 40px;
  text-align: center;
  &__ice {
    position: relative;
  }
  &__title {
    color: var(--yellow);
    margin-bottom: 12px;
  }
  .button {
    margin-top: 62px;
  }
}
.star {
  position: absolute;
  top: 10%; left: 45%;
  animation: star-ice 1.8s ease-in-out infinite alternate;
}
.disc-1 {
  position: absolute;
  top: 18%; left: 30%;
  animation: disc 3s ease-in-out infinite alternate;
}
.disc-2 {
  position: absolute;
  top: 30%; left: 5%;
  animation: disc 2s ease-in-out infinite alternate;
}
.disc-3 {
  position: absolute;
  top: 60%; left: 15%;
  animation: disc 1.5s ease-in-out infinite alternate;
}
.disc-4 {
  position: absolute;
  top: 70%; left: 65%;
  animation: disc 1s ease-in-out infinite alternate;
}
.disc-5 {
  position: absolute;
  top: 60%; left: 80%;
  animation: disc 2s ease-in-out infinite alternate;
}
.ice {
  animation: ice 1.8s ease-in-out infinite alternate;
}
.sticks-1 {
  position: absolute;
  top: 27%; left: 15%;
}
.sticks-2 {
  position: absolute;
  top: 75%; left: 75%;
}
.sticks-anim {
  animation: stick-anim 2s ease-in-out infinite alternate;
}
@keyframes stick-anim {
  0% {
    scale: 0.8;
  } 100% {
      scale: 1;
    }
}
@keyframes ice {
  0% {
    rotate: -3deg;
  } 100% {
        rotate: 10deg;
      }
}
@keyframes star-ice {
  0% {
    scale: 0.8;
  } 100% {
      scale: 1;
    }
}
@keyframes disc {
  0% {
    scale: 0.7;
  } 100% {
      scale: 1;
    }
}
</style>
