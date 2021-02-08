<template>
  <div class="popup">
    <div class="popup__inner">
      <div class="popup__text">
        <slot></slot>
      </div>
      <button class="popup__btn" @click="$emit('close-popup')">Закрыть</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Popup",
};
</script>

<style lang="scss" scoped>
.popup {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.438);

  display: flex;
  justify-content: center;
  align-items: center;
  &__inner {
    min-width: 300px;
    height: 150px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-radius: 5px;
    background-color: #fff;
  }
  &__text {
    margin-bottom: 20px;
    color: #000;
  }
  &__btn {
    margin-right: 10px;
    padding: 20px 40px;

    color: #fff;
    white-space: nowrap;
    text-transform: uppercase;
    outline: none;

    background: #0b48ff;

    transition: all 0.22s;
    &:hover {
      cursor: pointer;
      opacity: 0.8;
    }
    &:active {
      box-shadow: inset 1px 1px 1px rgba(0, 0, 0, 0.8);
    }
  }
}
</style>
