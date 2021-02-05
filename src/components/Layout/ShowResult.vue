<template>
  <div class="show-result">
    <div class="show-result__title">Проверьте данные пациента:</div>
    <div class="show-result__inner">
      <table class="table table-scroll">
        <thead></thead>
        <tbody>
          <tr v-for="(value, name, index) in person" :key="index">
            <td>{{ namesFiled[index] }}</td>
            <td>{{ toLowerCase(value) }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    person: {
      type: Object,
      required: true,
    },
    namesFiled: {
      type: Array,
      required: true,
    },
    step: {
      type: Number,
    },
  },
  methods: {
    toLowerCase(str) {
      let string;
      typeof str === "string"
        ? (string = str.toLowerCase())
        : typeof str === "boolean"
        ? str === false
          ? (string = "-")
          : (string = "ДА")
        : null;
      return string;
    },
  },
};
</script>

<style lang="scss" scoped>
.show-result {
  flex-grow: 1;
  &__title {
    margin-bottom: 20px;
    font-weight: 700;
    font-size: 20px;
  }
  &__inner {
    display: flex;
    justify-content: center;
  }
}
</style>
