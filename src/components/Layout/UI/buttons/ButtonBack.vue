<template>
  <button class="btn-back" type="button" @click="$emit('button-back')">
    Назад
  </button>
</template>

<style lang="scss" scoped>
.btn-back {
  margin-right: 10px;
  padding: 10px 30px;
  border: 1px solid #e72525;
  border-radius: 99px;

  color: #fff;
  white-space: nowrap;
  text-transform: uppercase;
  outline: none;

  background: #e72525;

  transition: all 0.22s;
  &:hover {
    cursor: pointer;
    opacity: 0.8;
  }
  &:disabled {
    cursor: not-allowed;
    opacity: 1 !important;
    background: #eee !important;
    border-color: #ddd !important;
    color: #999 !important;
  }
  &:active {
    box-shadow: inset 1px 1px 1px rgba(0, 0, 0, 0.8);
  }
}
</style>
