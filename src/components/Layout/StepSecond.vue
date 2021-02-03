<template>
  <div class="form__step">
    <item-input
      v-model="person.index"
      :value="person.index"
      :label-title="'Индекс'"
      :id="'formIndex'"
      :typeInput="'number'"
      :dirty="validate.index.$dirty"
      :required="validate.index.required"
    ></item-input>
    <item-input
      v-model="person.country"
      :value="person.country"
      :label-title="'Страна'"
      :id="'formCountry'"
      :typeInput="'text'"
      :dirty="validate.country.$dirty"
      :required="validate.country.required"
    ></item-input>
    <item-input
      v-model="person.region"
      :value="person.region"
      :label-title="'Регион'"
      :id="'formRegion'"
      :typeInput="'text'"
      :dirty="validate.region.$dirty"
      :required="validate.region.required"
    ></item-input>
    <item-input
      v-model="person.city"
      :value="person.city"
      :label-title="'Город'"
      :id="'formCity'"
      :typeInput="'text'"
      :dirty="validate.city.$dirty"
      :required="validate.city.required"
    ></item-input>
    <item-input
      v-model="person.street"
      :value="person.street"
      :label-title="'Улица'"
      :id="'formStreet'"
      :typeInput="'text'"
      :dirty="validate.street.$dirty"
      :required="validate.street.required"
    ></item-input>
    <item-input
      v-model="person.house"
      :value="person.house"
      :label-title="'Номер дома'"
      :id="'formHouse'"
      :typeInput="'number'"
      :dirty="validate.house.$dirty"
      :required="validate.house.required"
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
