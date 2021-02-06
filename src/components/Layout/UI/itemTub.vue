<template>
  <div class="steps__step" :class="classObject"></div>
</template>

<script>
export default {
  props: {
    step: {
      type: Number,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
  },
  computed: {
    classObject() {
      return {
        active: this.index === this.step,
        primary: this.index < this.step,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.steps__step {
  width: 50px;
  margin-right: 10px;
  padding: 10px 30px;
  border-bottom: 1px solid #000;

  cursor: default;
}

.active {
  background: #db8e00;
  color: #fff;
  border-color: #db8e00;
}

.primary {
  background: #42b983;
  color: #fff;
  border-color: #42b983;
}
</style>
