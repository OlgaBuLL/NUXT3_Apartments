<template>
  <div class="purchase-options">
    <div class="scroll">
      <h2>
        scroll <br />
        to see some animation
      </h2>
    </div>
    <div class="purchase-options__header">
      <h2 class="purchase-options__title">Варианты покупки</h2>

      <div class="purchase-options__buttons">
        <button>Подробнее</button>

        <div class="slider-buttons">
          <!-- prev btn -->
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 62 62"
            fill="none"
          >
            <g>
              <path
                d="M1 30.8125C1 47.381 14.4315 60.8125 31 60.8125C47.5685 60.8125 61 47.381 61 30.8125C61 14.244 47.5685 0.8125 31 0.8125C14.4315 0.8125 1 14.244 1 30.8125Z"
              />
              <path
                d="M26.5 29.9465C25.8333 30.3314 25.8333 31.2936 26.5 31.6785L32.5 35.1426C33.1667 35.5275 34 35.0464 34 34.2766L34 27.3484C34 26.5786 33.1667 26.0975 32.5 26.4824L26.5 29.9465Z"
              />
            </g>
          </svg>

          <!-- next btn -->
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 62 62"
            fill="none"
          >
            <g>
              <path
                d="M61 30.8125C61 47.381 47.5685 60.8125 31 60.8125C14.4315 60.8125 1 47.381 1 30.8125C1 14.244 14.4315 0.8125 31 0.8125C47.5685 0.8125 61 14.244 61 30.8125Z"
              />
              <path
                d="M35.5 29.9465C36.1667 30.3314 36.1667 31.2936 35.5 31.6785L29.5 35.1426C28.8333 35.5275 28 35.0464 28 34.2766L28 27.3484C28 26.5786 28.8333 26.0975 29.5 26.4824L35.5 29.9465Z"
              />
            </g>
          </svg>
        </div>
      </div>
    </div>

    <Card />

    <Application />
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
@import "../assets/styles/main.scss";

.scroll {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  & h2 {
    font-family: $main-font;
    text-align: center;
    color: rgb(8, 62, 76, 0.4);
  }
}
.purchase-options {
  &__header {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 1.5rem;
  }
  &__title {
    color: $dark_color;
    font-family: "Gilroy";
    // font-size: 42px;
    font-size: calc(26px + 16 * (100vw / 1440));
    font-weight: 500;
    line-height: 120%;
  }
  &__buttons {
    display: flex;
    gap: 20px;
    & button {
      background: $white-color;
      color: $accent-color;
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
        color: $white-color;
      }
    }
  }
}
.slider-buttons {
  display: flex;
  gap: 12px;
  & svg {
    max-width: 60px;
    width: 100%;
    max-height: 60px;
    cursor: pointer;
    transition: $transition;
    & g {
      opacity: 0.4;
      & path:first-child {
        stroke: $accent-color;
      }
      & path:last-child {
        fill: $accent-color;
      }
    }
  }

  // hover
  & svg:hover {
    transform: scale(1.1);
    & g {
      opacity: 1;
      & path:first-child {
        fill: $accent-hover;
      }
      & path:last-child {
        fill: $white-color;
      }
    }
  }
  // active
  & svg:active {
    transform: scale(1);
    & g {
      opacity: 1;
      & path:first-child {
        fill: none;
        stroke: $accent-color;
      }
      & path:last-child {
        fill: $accent-color;
      }
    }
  }
}

@media screen and (max-width: 500px) {
  .purchase-options {
    &__title {
      font-size: calc(26px + (16 + 16 * 0.7) * ((100vw - 320px) / 1440));
      font-weight: 500;
      line-height: 120%;
    }
  }
}
</style>
