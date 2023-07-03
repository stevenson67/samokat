<template>
  <section class="orders">
    <div class="container">
      <h2 class="orders-title">Больше заказов — больше призов</h2>
      <div class="orders-disc">
        <svg width="29" height="29" viewBox="0 0 29 29" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M9.39353 27.4878C2.06401 25.3145 -1.01007 17.939 1.16314 10.6095C3.33635 3.27993 11.0398 -0.900083 18.3694 1.27313C25.6989 3.44633 29.8789 11.1498 27.7057 18.4793C25.5325 25.8089 16.723 29.661 9.39353 27.4878Z" fill="#FFF3CA"/>
        </svg>
      </div>
      <ul class="orders-items">
        <li class="orders-item">
          Для участия в розыгрыше перейдите в подборку «До 500 рублей» и выберите любимые сладости.
        </li>
        <li class="orders-item">
          Чтобы открыть новые вкусы, миксуйте драже и мороженое. Например, попробуйте соединить кислые конфеты и карамельное мороженое.
        </li>
        <li class="orders-item">
          После заказа вы получите СМС с кодом, который нужно ввести на этом сайте.
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  name: "orders"
}
</script>

<style lang="scss">
.orders {
  margin: 60px 0;
  &-title {
    font-weight: 500;
    font-size: 30px;
    line-height: 32px;
    color: var(--yellow);
    margin-bottom: 40px;
  }
  &-disc {
    position: relative;
    svg {
      position: absolute;
      right: 0; top: -40px;
    }
  }
  &-items {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 0 34px;
  }
  &-item {
    font-size: 14px;
  }
}
</style>
