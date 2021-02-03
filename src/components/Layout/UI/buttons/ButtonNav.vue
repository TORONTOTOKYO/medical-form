<template>
  <div class="get-button">
    <button-back
      @button-back="$emit('button-back')"
      :disabled="disabledButtonBack"
    ></button-back>
    <button-next
      @button-next="$emit('button-next')"
      v-show="buttonNextShow"
    ></button-next>
    <button-finish v-show="buttonFinishShow"></button-finish>
  </div>
</template>

<script>
import ButtonBack from "@/components/Layout/UI/buttons/ButtonBack";
import ButtonNext from "@/components/Layout/UI/buttons/ButtonNext";
import ButtonFinish from "@/components/Layout/UI/buttons/ButtonFinish";

export default {
  components: {
    ButtonBack,
    ButtonNext,
    ButtonFinish,
  },
  props: {
    step: {
      type: Number,
    },
  },

  computed: {
    disabledButtonBack() {
      return this.step === 1 ? true : false;
    },
    buttonFinishShow() {
      return this.step === 4 ? true : false;
    },
    buttonNextShow() {
      return this.step < 4 ? true : false;
    },
  },
};
</script>
