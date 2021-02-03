<template>
  <button class="get-button" type="button" @click="$emit('button-next')">
    Далее
  </button>
</template>

<style lang="scss" scoped>
.get-button {
  color: #42b983;

  border-radius: 99px;
  letter-spacing: 0.05em;
  border: 1px solid #42b983;

  margin-right: 10px;
  padding: 10px 30px;

  white-space: nowrap;
  text-decoration: none;
  text-transform: uppercase;
  outline: none;

  background: #fff;

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
