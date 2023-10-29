<template>
  <div class="calculator">
    <h3 class="calculator__title">Ипотечный калькулятор</h3>

    <div class="calculator__content">
      <!-- Стоимость -->
      <div class="calculator__wrapper">
        <label class="calculator__label" for="price">Стоимость, млн ₽</label>
        <div class="calculator__range calculator__price">
          <div>
            <span>5,6</span>
            <span>|</span>
            <span>5,6</span>
          </div>

          <input type="range" id="price" />
        </div>
      </div>

      <!-- Checkbox -->
      <div class="calculator__checkboxes">
        <div>
          <input type="checkbox" name="flat" id="flat" />
          <label class="calculator__label" for="flat">Квартира</label>
        </div>

        <div>
          <input type="checkbox" name="apartment" id="apartment" />
          <label class="calculator__label" for="apartment">Апартамент</label>
        </div>
      </div>

      <!-- Первоначальный взнос -->
      <div class="calculator__wrapper">
        <label class="calculator__label" for="initial-payment"
          >Первоначальный взнос, ₽</label
        >
        <div class="calculator__range calculator__initial-payment">
          <div>
            <span>{{ formattedPayment }}</span>
            <span>30 %</span>
          </div>

          <input
            type="range"
            id="initial-payment"
            v-model="initialPayment"
            min="500000"
            max="5000000"
          />
        </div>
      </div>

      <!-- Срок выплат -->
      <div class="calculator__wrapper">
        <label class="calculator__label" for="payment-period"
          >Срок выплат</label
        >
        <div class="calculator__range calculator__payment-period">
          <span>{{ paymentPeriod }} лет</span>
          <input
            type="range"
            id="payment-period"
            max="30"
            v-model="paymentPeriod"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const paymentPeriod = ref(5);
const initialPayment = ref(1000000);

const formattedPayment = computed(() => {
  return initialPayment.value.toLocaleString("ru-RU");
});
</script>

<style lang="scss" scoped>
@import "../assets/styles/main.scss";

.calculator {
  max-width: 420px;
  width: 100%;
  height: fit-content;
  display: flex;
  flex-direction: column;
  gap: 30px;
  border-radius: 40px;
  border: 1px solid $accent-color;
  padding: 25px 35px 41px;
  &__content {
    display: flex;
    flex-direction: column;
    row-gap: 34px;
  }
  &__title {
    max-width: fit-content;
    background: rgba(8, 62, 76, 0.5);
    color: $white-color;
    font-family: "Gilroy";
    font-size: 14px;
    font-weight: 500;
    line-height: 100%;
    border-radius: 10px;
    padding: 10px;
    transition: $transition;
  }
  &__wrapper {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 13px;
  }
  &__label {
    color: $dark_color;
    font-family: "Gilroy";
    font-size: 14px;
    font-weight: 500;
    line-height: 100%;
  }
  &__range {
    position: relative;
    height: 58px;
    border-radius: 100px;
    background: #f1f5f5;
    border: 1px solid transparent;
    box-shadow: 0px 4px 15px 0px rgba(0, 0, 0, 0.02);
    padding: 20px;
    transition: $transition;
    cursor: pointer;
    &:hover {
      background: $white-color;
      border: 1px solid #026d89;
      & input {
        background: $accent-hover;
        &::-webkit-slider-thumb {
          background: $accent-hover;
        }
        &::-moz-range-thumb {
          background: $accent-hover;
        }
      }
    }
    & input {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      bottom: 0;
      width: calc(100% - 50px);
      height: 2px !important;
      background: $accent-color;
      border: none;
      outline: none;
      appearance: none;
    }
  }
}

.calculator {
  &:hover {
    border: 1px solid $accent-hover;
    & .calculator__title {
      background: $accent-hover;
    }
  }
}

.calculator__checkboxes {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  & div {
    display: flex;
    align-items: center;
    gap: 10px;

    & input[type="checkbox"] {
      cursor: pointer;
      position: relative;
      width: 22px;
      height: 22px;
      outline: none;
      border: none;

      &::before,
      &::after {
        content: "";
        position: absolute;
      }

      &::before {
        top: -3px;
        left: -3px;
        width: 25px;
        height: 25px;
        background: $white-color;
        border: 1px solid rgba(8, 62, 76, 0.5);
        border-radius: 6px;
      }

      &::after {
        transition: transform 0.4s cubic-bezier(0.45, 1.8, 0.5, 0.75);
        transform: rotate(-45deg) scale(0);
        top: 4px;
        left: 3px;
        width: 0.75rem;
        height: 0.375rem;
        border: 3px solid $accent-hover;
        border-top-style: none;
        border-right-style: none;
        border-radius: 1px;
        z-index: 1;
      }
      &:checked::after {
        transform: rotate(-45deg) scale(1.1);
      }
    }
  }
}

.calculator__price {
  & div {
    display: flex;
    justify-content: space-between;
    & span {
      color: #545863;
      font-family: "Gilroy";
      font-size: 16px;
      font-weight: 500;
    }
  }
}

.calculator__initial-payment {
  & div {
    display: flex;
    justify-content: space-between;
    & span {
      font-family: "Gilroy";
      font-size: 16px;
      font-weight: 500;
    }
    & span:first-child {
      color: #545863;
    }
    & span:last-child {
      color: $accent-color;
    }
  }
}

.calculator__payment-period {
  & span {
    color: #545863;
    font-family: "Gilroy";
    font-size: 16px;
    font-weight: 500;
  }
}

// Для Opera, Chrome, Edge
input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  width: 12px;
  height: 12px;
  border-radius: 40px;
  border: 2px solid #f5f7f5;
  background: $accent-color;
  cursor: pointer;
}

// Для Fire Fox
input[type="range"]::-moz-range-thumb {
  -webkit-appearance: none;
  width: 12px;
  height: 12px;
  border-radius: 40px;
  border: 2px solid #f5f7f5;
  background: $accent-color;
  cursor: pointer;
}
</style>
