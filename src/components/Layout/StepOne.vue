<template>
  <div class="form__step">
    <v-input
      v-model.trim="person.surname"
      :value="person.surname"
      :label-title="'Фамилия'"
      :id="'formSurname'"
      :typeInput="'text'"
      :dirty="validate.surname.$dirty"
      :required="validate.surname.required"
      :necessarily="true"
    ></v-input>

    <v-input
      v-model.trim="person.name"
      :value="person.name"
      :label-title="'Имя'"
      :id="'formName'"
      :typeInput="'text'"
      :dirty="validate.name.$dirty"
      :required="validate.name.required"
      :necessarily="true"
    ></v-input>
    <v-input
      v-model.trim="person.patronymic"
      :value="person.patronymic"
      :label-title="'Отчество'"
      :id="'formPatronymic'"
      :typeInput="'text'"
      :dirty="validate.patronymic.$dirty"
      :required="validate.patronymic.required"
      :necessarily="true"
    ></v-input>

    <v-datapicker
      v-model="person.dateOfBirth"
      :value="person.dateOfBirth"
      :dirty="validate.patronymic.$dirty"
      :required="validate.patronymic.required"
      :necessarily="true"
    ></v-datapicker>
    <v-input
      v-model.trim="person.phone"
      :value="person.phone"
      :label-title="'Номер телефона'"
      :id="'phoneForm'"
      :typeInput="'number'"
      :dirty="validate.phone.$dirty"
      :required="validate.phone.required"
      :necessarily="true"
    ></v-input>
    <v-select
      v-model="person.gender"
      :value="person.gender"
      :label-title="'Выберите пол'"
      :id="'formGender'"
      :list="gender"
      :dirty="validate.gender.$dirty"
      :required="validate.gender.required"
      :necessarily="true"
    ></v-select>
    <v-multi-select
      v-model="person.group"
      :value="person.group"
      :label-title="'Группа клиентов'"
      :id="'formClients'"
      :list="clients"
      :dirty="validate.group.$dirty"
      :required="validate.group.required"
      :necessarily="true"
    ></v-multi-select>
    <v-select
      v-model="person.doctor"
      :value="person.doctor"
      :label-title="'Выберите врача'"
      :id="'formDoctor'"
      :list="doctor"
      :dirty="validate.doctor.$dirty"
      :required="validate.doctor.required"
      :necessarily="true"
    ></v-select>
    <v-checkbox
      v-model="person.sms"
      :value="person.sms"
      :labelTitle="'Не отправлять SMS'"
      :id="'formSms'"
    ></v-checkbox>
  </div>
</template>

<script>
import VInput from "@/components/Layout/UI/VInput";
import VDatapicker from "@/components/Layout/UI/VDatapicker";
import VSelect from "@/components/Layout/UI/VSelect";
import VMultiSelect from "@/components/Layout/UI/VMultiSelect";
import VCheckbox from "@/components/Layout/UI/VCheckbox";

export default {
  name: "StepOne",
  components: {
    VInput,
    VDatapicker,
    VSelect,
    VMultiSelect,
    VCheckbox,
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
    gender: {
      type: Array,
      required: true,
    },
    doctor: {
      type: Array,
      required: true,
    },
    clients: {
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

<style lang="scss" scoped>
.form__step {
  flex-grow: 1;
}
</style>
