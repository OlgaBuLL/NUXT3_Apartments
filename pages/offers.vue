<template>
  <div class="more-offers">
    <h2 class="more-offers__title">Больше предложений здесь</h2>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
@import "../assets/styles/main.scss";

.more-offers {
  display: flex;
  justify-content: center;
  &__title {
    color: $accent-hover;
    font-family: $main-font;
    text-align: center;
  }
}
</style>
