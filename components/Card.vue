<template>
  <div class="cards">
    <!-- Ипотека -->

    <div class="card">
      <div class="card__picture">
        <img src="../assets/images/photo-1.webp" alt="Apartments" />
      </div>

      <div class="card__content">
        <h3 class="card__title">Ипотека от 4,3%</h3>

        <div class="card__info">
          <div class="card__text">
            <hr />
            <p>
              Выгодные условия при оформлении <br />
              у банков-партнеров
            </p>
          </div>

          <div class="card__play">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 65 66"
              fill="none"
            >
              <circle cx="32.5" cy="33.3125" r="32.5" fill="#083E4C" />
              <path
                d="M40.3889 33.1687C41.0556 33.5536 41.0556 34.5158 40.3889 34.9007L30.3889 40.6742C29.7222 41.0591 28.8889 40.578 28.8889 39.8082L28.8889 28.2612C28.8889 27.4914 29.7222 27.0103 30.3889 27.3952L40.3889 33.1687Z"
                fill="white"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>

    <!-- Рассрочка -->
    <div class="card">
      <div class="card__picture">
        <img src="../assets/images/photo-2.webp" alt="Apartments" />
      </div>

      <div class="card__content">
        <h3 class="card__title">Рассрочка 0%</h3>

        <div class="card__info">
          <div class="card__text">
            <hr />
            <p>
              Гибкие условия по размеру первоначального взноса, платежам и
              срокам
            </p>
          </div>

          <div class="card__play">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 65 66"
              fill="none"
            >
              <circle cx="32.5" cy="33.3125" r="32.5" fill="#083E4C" />
              <path
                d="M40.3889 33.1687C41.0556 33.5536 41.0556 34.5158 40.3889 34.9007L30.3889 40.6742C29.7222 41.0591 28.8889 40.578 28.8889 39.8082L28.8889 28.2612C28.8889 27.4914 29.7222 27.0103 30.3889 27.3952L40.3889 33.1687Z"
                fill="white"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>

    <!-- Покупка в Trade-in -->
    <div class="card">
      <div class="card__picture">
        <img src="../assets/images/photo-3.webp" alt="Apartments" />
      </div>

      <div class="card__content">
        <h3 class="card__title">Покупка в Trade-in</h3>

        <div class="card__info">
          <div class="card__text">
            <hr />
            <p>
              Выгодный обмен старой квартиры на новую квартиру или апартаменты
            </p>
          </div>

          <div class="card__play">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 65 66"
              fill="none"
            >
              <circle cx="32.5" cy="33.3125" r="32.5" fill="#083E4C" />
              <path
                d="M40.3889 33.1687C41.0556 33.5536 41.0556 34.5158 40.3889 34.9007L30.3889 40.6742C29.7222 41.0591 28.8889 40.578 28.8889 39.8082L28.8889 28.2612C28.8889 27.4914 29.7222 27.0103 30.3889 27.3952L40.3889 33.1687Z"
                fill="white"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  gsap.from(".card", {
    scrollTrigger: {
      trigger: ".card",
      toggleActions: "restart pause resume pause",
      // start: "top bottom",
      // end: "bottom center",
    },
    duration: 1,
    y: 60,
    opacity: 0,
    stagger: 0.3,
  });
});

// play
// pause
// resume
// reverse
// restart
// reset
// complete
// none
</script>

<style lang="scss" scoped>
@import "../assets/styles/main.scss";

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 34px;
  margin: 43px 0 75px;
}

.card {
  position: relative;
  max-width: 420px;
  width: 100%;
  height: 302px;
  border-radius: 2rem;
  overflow: hidden;
  outline: 1px solid #fff;

  &__picture {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: inherit;
    -moz-border-radius: inherit;
    -webkit-border-radius: inherit;
    transition: $transition;
    z-index: -1;
    & img {
      object-fit: cover;
      width: 100%;
      height: 100%;
      display: block;
      border-radius: inherit;
      -moz-border-radius: inherit;
      -webkit-border-radius: inherit;
    }
  }
  &__content {
    height: 100%;
    display: grid;
    grid-template-rows: 1fr 42%;
    background: linear-gradient(
      0deg,
      rgba(0, 0, 0, 0.7) 31.33%,
      rgba(0, 0, 0, 0) 59.93%
    );
    padding: 20px 0 0 20px;
    border-radius: inherit;
    outline: 1px solid #fff;
  }

  &__title {
    max-width: fit-content;
    background: $white-color;
    color: #545863;
    font-family: $main-font;
    font-size: 26px;
    font-weight: 500;
    line-height: 130%;
    border-radius: 10px;
    padding: 10px 12px;
    align-self: start;
    transition: $transition;
  }
  &__info {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 10px;
  }

  &__text {
    display: flex;
    flex-direction: column;
    gap: 18px;
    & hr {
      width: 100%;
      height: 1px;
      background: $white-color;
    }
    & p {
      color: $white-color;
      font-family: $main-font;
      // font-size: 16px;
      font-size: calc(12px + 4 * (100vw / 1440));
      font-weight: 500;
      line-height: 140%;
    }
  }
  &__play {
    width: 100%;
    align-self: flex-end;
    position: relative;
    background: $white-color;
    // padding: 10px 0 0 10px;
    padding: 10px;
    border-radius: 50% 0 2rem 0;
    z-index: 10;
    cursor: pointer;
    box-shadow: 1px 1px 1px #fff;

    & svg {
      position: relative;
      max-width: 65px;
      width: 100%;
      transition: $transition;
      z-index: 2;
    }
    &::before {
      content: "";
      position: absolute;
      left: -48px;
      // left: -64%;
      bottom: 0;
      width: 3rem;
      height: 3rem;
      background: transparent;
      border-radius: 0 0 70% 0;
      box-shadow: 10px 10px #fff;
      z-index: 1;
    }
    &::after {
      content: "";
      position: absolute;
      top: -48px;
      right: 0;
      width: 3rem;
      height: 3rem;
      background: transparent;
      border-radius: 0 0 70% 0;
      box-shadow: 10px 10px #fff;
      z-index: 1;
    }
  }
}

.card:hover .card__picture {
  transform: scale(1.1);
}
.card:hover .card__title {
  background: $accent-hover;
  color: $white-color;
}
.card:hover .card__play svg {
  scale: 1.1;
  rotate: 90deg;
  & circle {
    fill: $accent-hover;
  }
}

@media screen and (max-width: 500px) {
  .card {
    &__text {
      & p {
        font-size: calc(12px + (4 + 4 * 0.7) * ((100vw - 320px) / 1440));
      }
    }
  }
}
</style>
