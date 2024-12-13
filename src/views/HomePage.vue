<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Meal Picker</ion-title>
        <ion-buttons slot="primary">
          <ion-button>
            Pick random
          </ion-button>
        </ion-buttons>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
          <ion-button fill="clear">Clear</ion-button>
        </ion-toolbar>
      </ion-header>

      <ion-content class="ion-padding">
        <ion-item v-for="(meal, index) in meals" :key="index">
          <ion-avatar slot="start">
            <div class="emoji">{{ meal.icon }}</div>
          </ion-avatar>
          <div class="label">
            <ion-label>{{ meal.title }}</ion-label>
          </div>
        </ion-item>
      </ion-content>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import meals from '@/data/meals.json'

function pickRandomMeal() {
  const randomMeal = meals[Math.floor(Math.random() * meals.length)];

  return randomMeal;
}
</script>

<style scoped>
.emoji {
  font-size: 24px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.label {
  display: flex;
  flex-direction: column;
}
</style>
