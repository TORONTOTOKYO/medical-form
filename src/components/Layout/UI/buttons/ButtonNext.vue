<template>
  <button class="btn-next" type="button" @click="$emit('button-next')">
    Далее
  </button>
</template>

<style lang="scss" scoped>
.btn-next {
  color: #42b983;

  border-radius: 99px;
  border: 1px solid #42b983;

  margin-right: 10px;
  padding: 10px 30px;

  white-space: nowrap;
  text-transform: uppercase;
  outline: none;

  background: #fff;

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
