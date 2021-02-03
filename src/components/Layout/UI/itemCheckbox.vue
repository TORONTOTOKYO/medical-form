<template>
  <div class="options">
    <input
      type="checkbox"
      class="options__input"
      id="formSMS"
      true-value="да"
      false-value="нет"
      :value="value"
      @input="$emit('input', $event.target.checked)"
    />
    <label for="formSMS" class="options__label">{{ labelTitle }}</label>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: Boolean,
    },
    id: {
      type: String,
      required: true,
    },
    labelTitle: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.options {
  margin-bottom: 20px;
  &__input {
    display: none;

    &:checked + .options__label::after {
      transform: scale(1);
    }
  }
  &__label {
    position: relative;
    display: flex;
    align-items: center;
    line-height: 140%;
    cursor: pointer;

    &::before {
      content: "";
      flex: 0 0 18px;
      align-self: center;
      height: 18px;
      margin-right: 15px;
      border: 1px solid #000;
    }
    &::after {
      content: "";
      position: absolute;
      top: 6px;
      left: 4px;
      width: 10px;
      height: 10px;
      background: #3673be;

      transform: scale(0);

      transition: transform 0.2s linear;
    }
  }
}
</style>
