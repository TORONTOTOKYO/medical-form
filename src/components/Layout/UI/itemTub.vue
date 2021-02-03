<template>
  <div class="steps__step" :class="classObject">
    <slot></slot>
  </div>
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
  padding: 10px 30px;
  border: 1px solid #2869b9;
  border-radius: 100px;
  color: #2869b9;

  cursor: default;
  &:not(:last-child) {
    margin-right: 30px;
  }
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
