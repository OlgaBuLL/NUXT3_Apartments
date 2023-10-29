<template>
  <div className="contacts">
    <a href="https://t.me/bio_ol23" title="Telegram" target="_blank">
      <box-icon
        name="telegram"
        type="logo"
        color="#005b73"
        size="md"
        animation="tada-hover"
        border="square"
      ></box-icon>
    </a>

    <a href="mailto:oska43@mail.ru" title="E-mail" target="_blank">
      <box-icon
        name="envelope"
        color="#005b73"
        size="md"
        animation="tada-hover"
        border="square"
      ></box-icon>
    </a>

    <a href="https://github.com/OlgaBuLL" title="GitHub" target="_blank">
      <box-icon
        name="github"
        type="logo"
        color="#005b73"
        size="md"
        animation="tada-hover"
        border="square"
      ></box-icon>
    </a>
  </div>
</template>

<script setup>
// import "boxicons";
</script>

<style lang="scss" scoped>
@import "../assets/styles/main.scss";

.contacts {
  position: fixed;
  max-width: fit-content;
  top: 50%;
  transform: translateY(-50%);
  right: 1rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background: #ffffffce;
  border-radius: 40px;
  border: 1px solid rgba(61, 69, 67, 0.4);
  backdrop-filter: blur(5px);
  padding: 1.2rem 0.8rem;
  z-index: 11;
}

@media screen and (max-width: 768px) {
  .contacts {
    display: none;
  }
}
</style>
