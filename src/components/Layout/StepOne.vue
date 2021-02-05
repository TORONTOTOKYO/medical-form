<template>
  <div class="form__step">
    <item-input
      v-model.trim="person.surname"
      :value="person.surname"
      :label-title="'Фамилия'"
      :id="'formSurname'"
      :typeInput="'text'"
      :dirty="validate.surname.$dirty"
      :required="validate.surname.required"
      :necessarily="true"
    ></item-input>

    <item-input
      v-model.trim="person.name"
      :value="person.name"
      :label-title="'Имя'"
      :id="'formName'"
      :typeInput="'text'"
      :dirty="validate.name.$dirty"
      :required="validate.name.required"
      :necessarily="true"
    ></item-input>
    <item-input
      v-model.trim="person.patronymic"
      :value="person.patronymic"
      :label-title="'Отчество'"
      :id="'formPatronymic'"
      :typeInput="'text'"
      :dirty="validate.patronymic.$dirty"
      :required="validate.patronymic.required"
      :necessarily="true"
    ></item-input>

    <item-datapicker
      v-model="person.dateOfBirth"
      :value="person.dateOfBirth"
      :necessarily="true"
    ></item-datapicker>
    <item-input
      v-model.trim="person.phone"
      :value="person.phone"
      :label-title="'Номер телефона'"
      :id="'phoneForm'"
      :typeInput="'number'"
      :dirty="validate.phone.$dirty"
      :required="validate.phone.required"
      :necessarily="true"
    ></item-input>
    <item-select
      v-model="person.gender"
      :value="person.gender"
      :label-title="'Выберите пол'"
      :id="'formGender'"
      :list="gender"
      :dirty="validate.gender.$dirty"
      :required="validate.gender.required"
      :necessarily="true"
    ></item-select>
    <item-multi-select
      v-model="person.group"
      :value="person.group"
      :label-title="'Группа клиентов'"
      :id="'formClients'"
      :list="clients"
      :dirty="validate.group.$dirty"
      :required="validate.group.required"
      :necessarily="true"
    ></item-multi-select>
    <item-select
      v-model="person.doctor"
      :value="person.doctor"
      :label-title="'Выберите врача'"
      :id="'formDoctor'"
      :list="doctor"
      :dirty="validate.doctor.$dirty"
      :required="validate.doctor.required"
      :necessarily="true"
    ></item-select>
    <item-checkbox
      v-model="person.sms"
      :value="person.sms"
      :labelTitle="'Не отправлять SMS'"
      :id="'formSms'"
    ></item-checkbox>
  </div>
</template>

<script>
import itemInput from "@/components/Layout/UI/itemInput";
import itemDatapicker from "@/components/Layout/UI/itemDatapicker";
import itemSelect from "@/components/Layout/UI/itemSelect";
import itemMultiSelect from "@/components/Layout/UI/itemMultiSelect";
import itemCheckbox from "@/components/Layout/UI/itemCheckbox";

export default {
  components: {
    itemInput,
    itemDatapicker,
    itemSelect,
    itemMultiSelect,
    itemCheckbox,
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
    },
  },
};
</script>

<style lang="scss" scoped>
.form__step {
  flex-grow: 1;
}
</style>
