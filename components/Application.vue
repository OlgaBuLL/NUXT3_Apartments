<template>
  <div class="application">
    <!-- Калькулятор -->
    <Calculator />

    <!-- Инфо по рассчетам -->
    <div class="application__details">
      <div class="details">
        <div class="details__more-offers">
          <div>
            Узнайте о других
            <NuxtLink to="./offers">интересных предложениях</NuxtLink>
          </div>
        </div>
        <h3 class="details__title">Ипотека 0.1%</h3>
        <div class="details__info">
          <div>
            <span>Ежемесячный платёж</span>
            <span>12 591 ₽</span>
          </div>

          <div>
            <span>Ставка</span>
            <span>0.1%</span>
          </div>

          <div>
            <span>Сумма кредита</span>
            <span>4 465 050 ₽</span>
          </div>

          <div>
            <span>Срок кредита</span>
            <span>5 лет</span>
          </div>
        </div>
      </div>

      <p class="application__text">
        Приведенные расчеты носят предварительный характер. Окончательный расчет
        суммы кредита и размер ежемесячного платежа производится банком после
        предоставления оценки платежеспособности клиента.
      </p>

      <button class="application__button">
        Подать заявку на точный расчёт
      </button>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
@import "../assets/styles/main.scss";

.application {
  display: flex;
  gap: 39px;

  &__text {
    color: #778478;
    font-family: "Gilroy";
    font-size: 14px;
    font-weight: 500;
    line-height: 140%;
    margin: 25px 0 40px;
  }
  &__button {
    background: $accent-color;
    color: $white-color;
    font-family: "Gilroy";
    font-size: 16px;
    font-weight: 500;
    border-radius: 100px;
    border: 1px solid $accent-color;
    padding: 20px 25px;
    transition: $transition;
    cursor: pointer;
    &:hover {
      background: $accent-hover;
    }
  }
}
.details {
  position: relative;
  max-width: 871px;
  width: 100%;
  background: $accent-color;
  padding: 60px 40px 37px;
  border-radius: 2rem;
  &__title {
    max-width: fit-content;
    background: $white-color;
    color: $accent-color;
    font-family: "Gilroy";
    // font-size: 74px;
    font-size: calc(32px + 42 * (100vw / 1440));
    font-weight: 500;
    line-height: 110%;
    border-radius: 16px;
    padding: 12px 15px;
    margin-bottom: 50px;
  }
  &__info {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 2rem;
    & div {
      display: flex;
      flex-direction: column;
      gap: 16px;
      & span {
        font-family: "Gilroy";
        font-weight: 500;
      }
      & span:first-child {
        color: rgba(255, 255, 255, 0.7);
        font-size: 14px;
        line-height: 100%;
      }
      & span:last-child {
        color: $white-color;
        font-size: 30px;
        line-height: 120%;
      }
    }
  }
}

.details__more-offers {
  position: absolute;
  right: -1px;
  top: -1px;
  background: $white-color;
  color: $dark_color;
  font-family: "Gilroy";
  font-size: 14px;
  font-weight: 500;
  padding: 5px 1px 20px 20px;
  border-radius: 0 2rem 0 2rem;
  & a {
    color: $accent-color;
    text-decoration: none;
    transition: $transition;
    &:hover {
      color: $accent-hover;
    }
  }
  & div {
    position: relative;
    &::before {
      content: "";
      position: absolute;
      left: -51px;
      top: -7px;
      width: 34px;
      height: 30px;
      background: transparent;
      border-radius: 0 100% 0 0;
      box-shadow: 10px -10px #fff;
      z-index: 1;
    }
    &::after {
      content: "";
      position: absolute;
      right: 0;
      bottom: -68px;
      width: 3rem;
      height: 3rem;
      background: transparent;
      border-radius: 0 2rem 0 0;
      box-shadow: 10px -10px #fff;
      z-index: 1;
    }
  }
}

@media screen and (max-width: 900px) {
  .application {
    flex-wrap: wrap;
  }
}

@media screen and (max-width: 500px) {
  .details {
    padding: 60px 20px 37px;
    &__title {
      font-size: calc(32px + (42 + 42 * 0.7) * ((100vw - 320px) / 1440));
    }
  }
}
</style>
