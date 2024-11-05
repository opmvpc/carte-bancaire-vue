<script setup>
import CardForm from "./components/CardForm.vue";
import CardViewer from "./components/CardViewer.vue";
import { ref } from "vue";

const card = ref({
  name: "",
  number: "",
  expiration_month: "00",
  expiration_year: "00",
});
</script>

<template>
  <main>
    <CardForm v-model="card"></CardForm>
    <CardViewer :card="card"></CardViewer>
  </main>
</template>
