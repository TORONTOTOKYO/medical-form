<template>
  <div class="select">
    <label :for="id" class="select__label"
      >{{ labelTitle }}
      <span class="necessarily" v-if="necessarily">*</span></label
    >
    <select
      :id="id"
      class="select__item"
      :value="value"
      @input="$emit('input', $event.target.value)"
    >
      <option disabled value="">Выберите один из вариантов</option>
      <option
        class="select__options"
        v-for="(item, index) in list"
        :key="index"
        >{{ item }}</option
      >
    </select>
    <div class="error" v-if="dirty && !required">
      Это поле должно быть заполнено
    </div>
  </div>
</template>

<script>
export default {
  props: {
    necessarily: {
      type: Boolean,
    },
    value: {
      type: String,
    },
    labelTitle: {
      type: String,
      required: true,
    },
    list: {
      type: Array,
      required: true,
    },
    id: {
      type: String,
      required: true,
    },
    important: {
      type: Boolean,
    },
    dirty: {
      type: Boolean,
    },
    required: {
      type: Boolean,
    },
  },
};
</script>

<style lang="scss" scoped>
.select {
  position: relative;
  margin-bottom: 20px;

  &__label {
    display: block;
    margin-bottom: 10px;
    &::after {
      content: "";
      position: absolute;
      display: block;
      top: 40px;
      right: 10px;
      z-index: 1;
      pointer-events: none;

      border-style: solid;
      border-width: 8px 7px 0 9px;
      border-color: #121212 transparent transparent transparent;
    }
  }

  &__item {
    width: 100%;
    padding: 10px;

    border: 1px solid #ccc;
    border-radius: 3px;
    appearance: none;
    font-family: inherit;
    font-size: 16px;

    background: none;
    &::after {
      content: "";
      position: absolute;
      display: block;
      top: 0;
      right: 10px;
      z-index: 1;
      pointer-events: none;

      border-style: solid;
      border-width: 8px 7px 0 9px;
      border-color: #121212 transparent transparent transparent;
    }
    &:focus {
      border-color: #000;
    }
  }
  &__options {
    margin-bottom: 5px;
  }
  .error {
    margin: 5px 0px;
    font-size: 12px;
    color: red;
  }
  .necessarily {
    color: red;
  }
}
</style>
