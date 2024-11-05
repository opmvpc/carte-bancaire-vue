<script setup>
defineProps(["card"]);
</script>

<template>
  <h2>Prévisualisation</h2>
  <div>
    <dl>
      <dt>Nom :</dt>
      <dd>{{ card.name }}</dd>
      <dt>Numéro :</dt>
      <dd>{{ card.number }}</dd>
      <dt>Date d'expiration :</dt>
      <dd>{{ card.expiration_month }} / {{ card.expiration_year }}</dd>
    </dl>
  </div>
</template>
