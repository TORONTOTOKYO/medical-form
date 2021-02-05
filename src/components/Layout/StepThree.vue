<template>
  <div class="form__step">
    <item-select
      v-model.trim="person.document"
      :value="person.document"
      :label-title="'Выберите тип документа'"
      :id="'formDocument'"
      :list="document"
      :dirty="validate.document.$dirty"
      :required="validate.document.required"
      :necessarily="true"
    ></item-select>
    <item-input
      value="person.series"
      v-model.trim="person.series"
      :label-title="'Серия документа'"
      :id="'formSeries'"
      :necessarily="false"
    ></item-input>
    <item-input
      value="person.number"
      v-model.trim="person.number"
      :label-title="'Номер документа'"
      :id="'formNumber'"
      :dirty="validate.number.$dirty"
      :required="validate.number.required"
      :necessarily="true"
    ></item-input>
    <item-input
      value="person.issued"
      v-model.trim="person.issued"
      :label-title="'Кем выдан'"
      :id="'formIssued'"
      :dirty="validate.issued.$dirty"
      :required="validate.issued.required"
      :necessarily="true"
    ></item-input>
    <item-input
      value="person.dateIssued"
      v-model.trim="person.dateIssued"
      :label-title="'Когда выдан'"
      :id="'formDataIssued'"
      :type="'number'"
      :dirty="validate.dateIssued.$dirty"
      :required="validate.dateIssued.required"
      :necessarily="true"
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
