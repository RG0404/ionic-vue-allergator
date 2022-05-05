<template>
  <ion-page>
    <ion-content>
        <div class="main-container">
            <img src="../../public/assets/logo-allergator.png" alt="Logo Allergator">
            <h1>Allergator</h1>
            <a href="/tabs/tab2" class="cta">GO</a>
        </div>
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

<style scoped>

ion-content {
    --background: #48BF53 !important;
}

.main-container {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.main-container img {
    margin-top: 120px;
}

.main-container h1 {
    font-family: peachy-keen-jf, sans-serif;
    font-size: 46px;
    margin-top: 40px;
    color: #fff;
}

.main-container .cta {
    background-color: #11823B;
    padding: 20px;
    border-radius: 50%;
    color: #fff;
    text-decoration: none;
    font-size: 50px;
    margin-top: 140px;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}

</style>