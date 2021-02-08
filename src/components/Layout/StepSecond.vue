<template>
  <div class="form__step">
    <v-input
      v-model.trim="person.index"
      :value="person.index"
      :label-title="'Индекс'"
      :id="'formIndex'"
      :typeInput="'number'"
      :necessarily="false"
    ></v-input>
    <v-input
      v-model.trim="person.country"
      :value="person.country"
      :label-title="'Страна'"
      :id="'formCountry'"
      :typeInput="'text'"
      :necessarily="false"
    ></v-input>
    <v-input
      v-model.trim="person.region"
      :value="person.region"
      :label-title="'Регион'"
      :id="'formRegion'"
      :typeInput="'text'"
      :necessarily="false"
    ></v-input>
    <v-input
      v-model.trim="person.city"
      :value="person.city"
      :label-title="'Город'"
      :id="'formCity'"
      :typeInput="'text'"
      :dirty="validate.city.$dirty"
      :required="validate.city.required"
      :necessarily="true"
    ></v-input>
    <v-input
      v-model.trim="person.street"
      :value="person.street"
      :label-title="'Улица'"
      :id="'formStreet'"
      :typeInput="'text'"
      :dirty="validate.street.$dirty"
      :required="validate.street.required"
      :necessarily="true"
    ></v-input>
    <v-input
      v-model.trim="person.house"
      :value="person.house"
      :label-title="'Номер дома'"
      :id="'formHouse'"
      :typeInput="'number'"
      :dirty="validate.house.$dirty"
      :required="validate.house.required"
      :necessarily="true"
    ></v-input>
  </div>
</template>

<script>
import VInput from "@/components/Layout/UI/VInput";
export default {
  name: "StepSecond",
  components: {
    VInput,
  },
  props: {
    step: {
      type: Number,
      required: true,
    },
    person: {
      type: Object,
      required: true,
    },
    validate: {
      type: Object,
      required: true,
    },
  },
};
</script>
