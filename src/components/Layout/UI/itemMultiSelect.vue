<template>
  <div class="select">
    <label :for="id" class="select__label"
      >{{ labelTitle }}
      <span class="necessarily" v-if="necessarily">*</span></label
    >
    <select
      :id="id"
      class="select__item"
      multiple
      :value="value"
      @input="$emit('input', $event.target.value)"
    >
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
    id: {
      type: String,
      required: true,
    },
    list: {
      type: Array,
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
    font-size: 16px;
  }

  &__item {
    width: 100%;
    padding: 10px;

    border: 1px solid #ccc;

    appearance: none;
    font-family: inherit;
    font-size: 16px;

    background: none;
    &:focus {
      border-color: #000;
    }
  }
  &__options {
    margin-bottom: 5px;
  }
  .error {
    font-size: 12px;
    color: red;
  }

  .necessarily {
    color: red;
  }
}
</style>
