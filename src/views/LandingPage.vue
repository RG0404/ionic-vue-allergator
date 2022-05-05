<template>
  <ion-page>
    <ion-content>
        <div class="hey">HELLO</div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonIcon, IonPage, IonContent } from '@ionic/vue';


export default defineComponent({
  name: 'TabsPage',
  components: { IonPage, IonContent },
  setup() {
    return {
      
    }
  }
});
</script>
