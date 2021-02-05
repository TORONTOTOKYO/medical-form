<template>
  <div class="container">
    <form class="form" @submit.prevent="onSubmit" novalidate>
      <div class="form__title">Форма регистрации клиента</div>
      <div class="steps">
        <item-tub
          v-for="(tab, index) in tabs"
          :key="index"
          :index="index + 1"
          :step="step"
          >{{ tab }}</item-tub
        >
      </div>
      <step-one
        v-show="step === 1"
        :step="step"
        :person="person"
        :gender="gender"
        :doctor="doctor"
        :clients="clients"
        :validate="$v.person"
      ></step-one>
      <step-second
        v-show="step === 2"
        :step="step"
        :person="person"
        :validate="$v.person"
      ></step-second>
      <step-three
        v-show="step === 3"
        :step="step"
        :person="person"
        :document="document"
        :validate="$v.person"
      ></step-three>
      <show-result
        v-show="step === 4"
        :person="showResults"
        :names-filed="namesField"
      ></show-result>
      <button-nav
        @button-next="buttonNext"
        @button-back="buttonBack"
        :step="step"
      ></button-nav>
    </form>
    <popup @close-popup="closePopup" v-if="popup.sucsess || popup.failed">{{
      textPopup
    }}</popup>
  </div>
</template>

<script>
import { required } from "vuelidate/lib/validators";
import itemTub from "@/components/Layout/UI/itemTub";

import StepOne from "@/components/Layout/StepOne";
import StepSecond from "@/components/Layout/StepSecond";
import StepThree from "@/components/Layout/StepThree";
import ShowResult from "@/components/Layout/ShowResult";
import Popup from "@/components/Layout/Popup";

import ButtonNav from "@/components/Layout/UI/buttons/ButtonNav";

export default {
  components: {
    itemTub,
    StepOne,
    StepSecond,
    StepThree,
    ShowResult,
    ButtonNav,
    Popup,
  },
  data() {
    return {
      person: {
        name: "",
        surname: "",
        patronymic: "",
        dateOfBirth: "",
        phone: "",
        gender: "",
        group: "",
        doctor: "",
        sms: "",
        index: "",
        country: "",
        region: "",
        city: "",
        street: "",
        house: "",
        document: "",
        series: "",
        number: "",
        issued: "",
        dateIssued: "",
      },
      popup: {
        sucsess: false,
        failed: false,
      },
      step: 1,
      chekedResult: false,
      tabs: ["Основная информация", "Адрес", "Документ", "Проверка данных"],
      gender: ["Мужской", "Женский"],
      doctor: ["Иванов", "Захаров", "Чернышёва"],
      clients: ["VIP", "Проблемные", "ОМС"],
      document: ["Паспорт РФ", "Паспорт моряка", "Водительское удостоверение"],
      namesField: [
        "Имя:",
        "Фамилия:",
        "Отчество:",
        "Дата Рождения:",
        "Номер телефона:",
        "Пол:",
        "Группа пациентов:",
        "Лечащий врач:",
        "Отправлять СМС:",
        "Индекс:",
        "Страна:",
        "Регион:",
        "Город:",
        "Улица:",
        "Дом:",
        "Документ:",
        "Серия:",
        "Номер:",
        "Кем выдан:",
        "Когда выдан",
      ],
    };
  },

  methods: {
    buttonNext() {
      this.step < 4 ? this.step++ : null;

      if (this.step === 4) {
        this.$v.person.$touch();
        if (this.$v.person.$error) {
          this.popup.failed = true;
          this.step = 1;
        }
      }
    },
    buttonBack() {
      this.step !== 1 ? this.step-- : null;
    },
    onSubmit(event) {
      this.popup.sucsess = true;
      event.target.reset();
      this.$v.person.$reset();
      this.step = 1;

      for (let key in this.person) {
        this.person[key] = "";
      }
    },
    closePopup() {
      this.popup.sucsess = this.popup.failed = false;
    },
    searchEmptyString(obj, searchString, installingString) {
      for (let key in obj) {
        obj[key] === searchString ? (obj[key] = installingString) : null;
      }
    },
  },
  computed: {
    showResults() {
      let obj = this.person;
      if (this.step === 4) {
        this.searchEmptyString(obj, "", "-");
      } else if (this.step < 4) {
        this.searchEmptyString(obj, "-", "");
      }
      return obj;
    },
    textPopup() {
      return this.popup.failed
        ? "Заполните все необходимые поля"
        : "Клиент создан";
    },
  },
  validations: {
    person: {
      name: {
        required,
      },
      surname: {
        required,
      },
      patronymic: {
        required,
      },
      phone: {
        required,
      },
      gender: {
        required,
      },
      group: {
        required,
      },
      doctor: {
        required,
      },

      city: {
        required,
      },
      street: {
        required,
      },
      house: {
        required,
      },
      document: {
        required,
      },
      series: {},
      number: {
        required,
      },
      issued: {
        required,
      },
      dateIssued: {
        required,
      },
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100vh;
  max-width: 992px;
  padding: 0px 10px;
  margin: 0 auto;
}

.form {
  width: 100%;
  min-height: 950px;
  display: flex;
  flex-direction: column;
  padding: 16px;
  margin-top: 16px;
  border-radius: 10px;

  color: #000;

  background: #fff;
  box-shadow: 2px 3px 10px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  &__title {
    font-size: 30px;
    font-weight: 700;
    margin: 0 auto 30px;
  }
  &__step {
    flex-grow: 1;
  }
}

.steps {
  display: flex;
  margin-bottom: 30px;
}
</style>
