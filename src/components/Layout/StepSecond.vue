<template>
  <div class="form__step">
    <item-input
      v-model.trim="person.index"
      :value="person.index"
      :label-title="'Индекс'"
      :id="'formIndex'"
      :typeInput="'number'"
      :necessarily="false"
    ></item-input>
    <item-input
      v-model.trim="person.country"
      :value="person.country"
      :label-title="'Страна'"
      :id="'formCountry'"
      :typeInput="'text'"
      :necessarily="false"
    ></item-input>
    <item-input
      v-model.trim="person.region"
      :value="person.region"
      :label-title="'Регион'"
      :id="'formRegion'"
      :typeInput="'text'"
      :necessarily="false"
    ></item-input>
    <item-input
      v-model.trim="person.city"
      :value="person.city"
      :label-title="'Город'"
      :id="'formCity'"
      :typeInput="'text'"
      :dirty="validate.city.$dirty"
      :required="validate.city.required"
      :necessarily="true"
    ></item-input>
    <item-input
      v-model.trim="person.street"
      :value="person.street"
      :label-title="'Улица'"
      :id="'formStreet'"
      :typeInput="'text'"
      :dirty="validate.street.$dirty"
      :required="validate.street.required"
      :necessarily="true"
    ></item-input>
    <item-input
      v-model.trim="person.house"
      :value="person.house"
      :label-title="'Номер дома'"
      :id="'formHouse'"
      :typeInput="'number'"
      :dirty="validate.house.$dirty"
      :required="validate.house.required"
      :necessarily="true"
    ></item-input>
  </div>
</template>

<script>
import itemInput from "@/components/Layout/UI/itemInput";
export default {
  components: {
    itemInput,
  },
  props: {
    step: {
      type: Number,
    },
    person: {
      type: Object,
      required: true,
    },
    validate: {
      type: Object,
    },
  },
};
</script>
