<template>
  <section class="certificates">
    <div class="container">
      <h2 class="certificates-title">Вот какие сертификаты можно выиграть:</h2>
      <div class="certificates-components">
        <div class="certificates-components-svg">
          <svg class="corn-1" width="61" height="69" viewBox="0 0 61 69" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M37.6033 1.85327C18.3648 0.528949 17.1679 13.9941 18.9742 20.8922C-2.20938 22.6741 2.45022 39.4475 7.42797 47.6114C0.956523 43.5579 3.85352 51.5904 8.11879 55.8294C23.1715 70.7897 43.2103 68.5103 53.7747 51.989C62.2263 38.7719 55.76 28.2196 51.4705 24.5957C54.8641 17.5667 56.8417 3.1776 37.6033 1.85327Z" fill="#FFF3CA"/>
          </svg>
          <certificates1/>
          <img class="snikers" src="/media/snikers.svg">
          <svg class="corn-2" width="30" height="30" viewBox="0 0 30 30" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M2.34351 25.1943C6.92347 33.2084 15.8548 27.7286 15.8548 27.7286C15.8548 27.7286 19.0047 33.2174 25.9335 26.2516C33.9144 18.2279 25.3223 7.46246 22.4761 8.44414C20.4046 9.15862 22.2625 6.62824 17.6449 2.22625C13.9509 -1.29535 7.56525 1.75403 6.5944 5.12821C2.71962 7.83014 3.80333 10.4622 5.51914 11.4932C2.14281 13.7835 -1.95789 17.6676 2.34351 25.1943Z" fill="#EFDDA2"/>
          </svg>
          <certifiactes2/>
          <svg class="corn-3" width="82" height="80" viewBox="0 0 82 80" fill="none" xmlns="http://www.w3.org/2000/svg">
            <g clip-path="url(#clip0_1028_1760)">
              <path d="M61.0055 65.0322C73.7473 51.2529 64.2678 42.1301 57.9353 39.2912C69.5085 22.1418 53.9474 15.4412 44.7202 14.2346C51.7421 11.8008 43.8841 9.09674 38.0675 9.74453C17.5403 12.0307 7.04269 28.6155 13.1244 46.7057C17.9897 61.1779 29.9359 62.713 35.3009 61.6715C38.56 68.5332 48.2638 78.8116 61.0055 65.0322Z" fill="#FFF3CA"/>
              <path d="M15.4753 1.17183C3.11563 3.06599 5.70157 17.0229 5.70157 17.0229C5.70157 17.0229 -2.76989 18.3368 2.66863 30.4843C8.93307 44.4765 26.7223 38.8471 26.8649 34.7712C26.9688 31.8046 29.2648 35.384 37.0757 31.686C43.3244 28.7276 42.5737 19.1712 38.7795 16.3031C37.2472 10.0902 33.3924 10.1806 31.2545 11.8487C30.0004 6.4662 27.0833 -0.60713 15.4753 1.17183Z" fill="#EFDDA2"/>
            </g>
            <defs>
              <clipPath id="clip0_1028_1760">
                <rect width="360" height="3739" fill="white" transform="translate(-110 -1785)"/>
              </clipPath>
            </defs>
          </svg>
          <svg class="corn-disc" width="21" height="20" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7.03389 19.3202C1.78745 17.7647 -0.412955 12.4853 1.14262 7.23884C2.69819 1.99241 8.21231 -0.999627 13.4587 0.555945C18.7052 2.11152 21.6972 7.62563 20.1416 12.8721C18.5861 18.1185 12.2803 20.8758 7.03389 19.3202Z" fill="#4CA859"/>
          </svg>
          <certificates3/>
        </div>
        <popcorn/>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "certificates"
}
</script>

<style lang="scss">
.certificates {
  &-title {
    font-size: 30px;
    line-height: 32px;
    color: var(--yellow);
  }
  &-components {
    display: flex;
    flex-direction: column;
    align-items: center;
    &-svg {
      position: relative;
      display: flex;
      flex-direction: column;
      gap: 32px;
    }
  }
}
.corn-1, .corn-2, .corn-3, .corn-3 path:nth-child(2), .corn-disc, .snikers {
  position: absolute;
}
.corn-1 {
  top: -10%;
  right: 10%;
  z-index: 4;
}
.snikers {
  top: 5%;
  left: 30%;
  width: 140px;
}
.corn-2 {
  top: 15%;
  left: 80%;
  z-index: -1;
}
.corn-3 {
  top: 30%;
  left: 20%;
}
.corn-3 path:nth-child(2) {
  left: 30px;
  transform: translate(40px, 15px);
}
.corn-disc {
  top: 66%;
  left: 80%;
}
</style>
