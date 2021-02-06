<template>
  <button class="btn" :type="typeButton" @click="$emit('button-click')">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    typeButton: {
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  margin-right: 5px;
  padding: 20px 50px;

  color: #fff;
  white-space: nowrap;
  letter-spacing: 2px;
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
</style>
