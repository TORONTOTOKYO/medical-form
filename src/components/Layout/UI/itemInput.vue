<template>
  <div class="form__item">
    <label :for="id" class="form__label"
      >{{ labelTitle }} <span class="form__span">*</span></label
    >
    <input
      :type="typeInput"
      class="form__input"
      :id="id"
      tabindex="1"
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
  props: {
    value: {
      type: String,
    },
    labelTitle: {
      type: String,
    },
    id: {
      type: String,
    },
    typeInput: {
      type: String,
      require: true,
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
.form__item {
  margin-bottom: 20px;
}
.form__label {
  display: block;
  margin-bottom: 10px;
}
.form__input {
  width: 80%;
  display: block;
  width: 100%;
  padding: 8px 24px;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  font-size: 16px;
  font-weight: 400;
  color: #2c3e50;

  box-shadow: 1px 2px 1px 0px rgba(0, 0, 0, 0.11);
  &:focus {
    border-color: #2c3e50;
    box-shadow: 1px 2px 1px 0px rgba(0, 0, 0, 0.21);
  }
}
.form__span {
  color: red;
}
.error {
  font-size: 12px;
  color: red;
}
</style>
