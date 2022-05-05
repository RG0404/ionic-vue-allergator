<template>
  <ion-page>
    <ion-content :fullscreen="true">
      
      <ion-header>
        <img src="../../public/assets/logo-allergator.png" alt="Logo Allergator">
        <h2>Historique</h2>
      </ion-header>
      
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonHeader, IonPage, IonContent } from '@ionic/vue';

export default defineComponent({
  name: 'Tab2Page',
  components: { IonContent, IonPage, IonHeader }
});
</script>

<style scoped>

ion-header {
  display: flex;
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: #f1f1f1;
}

ion-header img {
  width: 60px;
  margin-left: 20px;
}

ion-header h2 {
  font-family: peachy-keen-jf, sans-serif;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}

</style>