<script setup>
import { reactive } from "vue";

const card = defineModel();

const errors = reactive({
  name: "",
  number: "",
  expiration_month: "",
  expiration_year: "",
});

const validate = () => {
  // on reset les erreurs
  errors.name = "";
  errors.number = "";
  errors.expiration_month = "";
  errors.expiration_year = "";

  if (card.value.name.length === 0) {
    errors.name = "Le champs nom est requis.";
  }

  if (card.value.number.length !== 10) {
    errors.number = "Le champs numéro doit comporter 10 chiffres.";
  }

  if (card.value.expiration_month.length !== 2) {
    errors.expiration_month = "Le champs mois doit comporter 2 chiffres.";
  }
  if (card.value.expiration_year.length !== 2) {
    errors.expiration_year = "Le champs année doit comporter 2 chiffres.";
  }

  // plein d'autres vérifications à faire
};
</script>

<template>
  <h2>Formulaire</h2>
  <form @submit.prevent @input="validate">
    <div>
      <label for="name">Nom</label>
      <input id="name" type="text" v-model="card.name" />
      <span>{{ errors.name }}</span>
    </div>
    <div>
      <label for="number">Numéro</label>
      <input id="number" type="text" v-model="card.number" />
      <span>{{ errors.number }}</span>
    </div>
    <div>
      <label for="expiration_month">Mois</label>
      <input
        id="expiration_month"
        type="text"
        v-model="card.expiration_month"
      />
      <span>{{ errors.expiration_month }}</span>
    </div>
    <div>
      <label for="expiration_year">Année</label>
      <input id="expiration_year" type="text" v-model="card.expiration_year" />
      <span>{{ errors.expiration_year }}</span>
    </div>
  </form>
</template>
