<template>
  <div class="form__step">
    <item-select
      v-model="person.document"
      :value="person.document"
      :label-title="'Выберите тип документа'"
      :id="'formDocument'"
      :list="document"
      :dirty="validate.document.$dirty"
      :required="validate.document.required"
    ></item-select>
    <item-input
      value="person.series"
      v-model="person.series"
      :label-title="'Серия документа'"
      :id="'formSeries'"
      :dirty="validate.series.$dirty"
      :required="validate.series.required"
    ></item-input>
    <item-input
      value="person.number"
      v-model="person.number"
      :label-title="'Номер документа'"
      :id="'formNumber'"
      :dirty="validate.number.$dirty"
      :required="validate.number.required"
    ></item-input>
    <item-input
      value="person.issued"
      v-model="person.issued"
      :label-title="'Кем выдан'"
      :id="'formIssued'"
      :dirty="validate.issued.$dirty"
      :required="validate.issued.required"
    ></item-input>
    <item-input
      value="person.dateIssued"
      v-model="person.dateIssued"
      :label-title="'Когда выдан'"
      :id="'formDataIssued'"
      :type="'number'"
      :dirty="validate.dateIssued.$dirty"
      :required="validate.dateIssued.required"
    ></item-input>
  </div>
</template>

<script>
import itemInput from "@/components/Layout/UI/itemInput";
import itemSelect from "@/components/Layout/UI/itemSelect";
export default {
  components: {
    itemInput,
    itemSelect,
  },
  props: {
    step: {
      type: Number,
    },
    person: {
      type: Object,
      required: true,
    },
    document: {
      type: Array,
      required: true,
    },
    validate: {
      type: Object,
    },
  },
};
</script>
