<template>
  <ion-page>
    <ion-content :fullscreen="true">
      
      <BarcodeScanner />
      
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonContent } from '@ionic/vue';
import BarcodeScanner from '@/components/BarcodeScanner.vue'


export default defineComponent({
  name: 'Tab2Page',
  components: { IonContent, IonPage, BarcodeScanner }
});
</script>
