<template>
  <div class="form__item">
    <label :for="id" class="form__label"
      >{{ labelTitle }}
      <span class="necessarily" v-if="necessarily">*</span></label
    >
    <input
      :type="typeInput"
      class="form__input"
      :id="id"
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
  name: "itemInput",
  props: {
    necessarily: {
      type: Boolean,
      default: false,
    },
    value: {
      type: String,
      required: true,
    },
    labelTitle: {
      type: String,
      required: true,
    },
    id: {
      type: String,
      required: true,
    },
    typeInput: {
      type: String,
      require: true,
    },

    dirty: {
      type: Boolean,
      required: false,
    },
    required: {
      type: Boolean,
      required: false,
    },
    numeric: {
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
  font-size: 16px;
}
.form__input {
  width: 80%;
  display: block;
  width: 100%;
  padding: 15px 24px;
  border: 1px solid #e5e5e5;

  font-size: 16px;
  font-weight: 400;
  color: #2c3e50;

  &:focus {
    border-color: #2c3e50;
  }
}
.necessarily {
  color: red;
}
.error {
  font-size: 12px;
  color: red;
}
</style>
