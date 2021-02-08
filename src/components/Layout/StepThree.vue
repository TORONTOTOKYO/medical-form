<template>
  <div class="form__step">
    <v-select
      v-model.trim="person.document"
      :value="person.document"
      :label-title="'Выберите тип документа'"
      :id="'formDocument'"
      :list="document"
      :dirty="validate.document.$dirty"
      :required="validate.document.required"
      :necessarily="true"
    ></v-select>
    <v-input
      value="person.series"
      v-model.trim="person.series"
      :label-title="'Серия документа'"
      :id="'formSeries'"
      :necessarily="false"
    ></v-input>
    <v-input
      value="person.number"
      v-model.trim="person.number"
      :label-title="'Номер документа'"
      :id="'formNumber'"
      :dirty="validate.number.$dirty"
      :required="validate.number.required"
      :necessarily="true"
    ></v-input>
    <v-input
      value="person.issued"
      v-model.trim="person.issued"
      :label-title="'Кем выдан'"
      :id="'formIssued'"
      :dirty="validate.issued.$dirty"
      :required="validate.issued.required"
      :necessarily="true"
    ></v-input>
    <v-input
      value="person.dateIssued"
      v-model.trim="person.dateIssued"
      :label-title="'Когда выдан'"
      :id="'formDataIssued'"
      :type="'number'"
      :dirty="validate.dateIssued.$dirty"
      :required="validate.dateIssued.required"
      :necessarily="true"
    ></v-input>
  </div>
</template>

<script>
import VInput from "@/components/Layout/UI/VInput";
import VSelect from "@/components/Layout/UI/VSelect";
export default {
  name: "StepThree",
  components: {
    VInput,
    VSelect,
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
    document: {
      type: Array,
      required: true,
    },
    validate: {
      type: Object,
      required: true,
    },
  },
};
</script>
