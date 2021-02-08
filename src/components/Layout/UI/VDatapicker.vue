<template>
  <div class="form__item">
    <label for="formDateOfBirth" class="form__label"
      >Дата рождения
      <span class="necessarily" v-if="necessarily">*</span></label
    >
    <input
      type="date"
      class="form__input"
      id="formDateOfBirth"
      :value="value"
      @input="$emit('input', $event.target.value)"
    />
    <div class="error" v-if="dirty && !required">
      Это поле должно быть заполнено
    </div>
  </div>
</template>

<script>
export default {
  name: "itemDatapicker",
  props: {
    value: {
      type: String,
      required: true,
    },
    necessarily: {
      type: Boolean,
      default: false,
    },
    important: {
      type: Boolean,
      default: false,
    },
    dirty: {
      type: Boolean,
      default: false,
    },
    required: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
.form__item {
  margin-bottom: 20px;
}
.form__label {
  display: block;
  margin-bottom: 10px;
  font-size: 16px;
}
.form__input {
  width: 80%;
  display: block;
  width: 100%;
  padding: 8px 24px;
  border: 1px solid #e5e5e5;

  font-size: 16px;
  font-weight: 400;
  color: #2c3e50;

  &:focus {
    border-color: #2c3e50;
  }
}
.error {
  color: red;
}
</style>
