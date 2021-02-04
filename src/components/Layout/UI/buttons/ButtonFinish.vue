<template>
  <button class="btn-finish" type="submit">
    Готово
  </button>
</template>

<style lang="scss" scoped>
.btn-finish {
  border: 1px solid #2869b9;
  border-radius: 99px;

  margin-right: 10px;
  padding: 10px 30px;

  color: #fff;
  white-space: nowrap;
  text-decoration: none;
  text-transform: uppercase;
  outline: none;

  background: #2869b9;

  transition: all 0.22s;
  &:hover {
    cursor: pointer;
    opacity: 0.8;
  }
  &:active {
    box-shadow: inset 1px 1px 1px rgba(0, 0, 0, 0.8);
  }
}
</style>
