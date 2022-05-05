<template>
  <ion-page>

    <ion-fab vertical="bottom" horizontal="center" slot="fixed">
      <ion-fab-button href="/tabs/tab2">
        <ion-icon :icon="scan" />
      </ion-fab-button>
    </ion-fab>

    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button class="side-tab" tab="tab1" href="/tabs/tab1">
          <ion-icon :icon="list" />
        </ion-tab-button>
          
        <ion-tab-button tab="tab2" ></ion-tab-button>
        
        <ion-tab-button class="side-tab" tab="tab3" href="/tabs/tab3">
          <ion-icon :icon="person" />
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonTabBar, IonTabButton, IonTabs, IonIcon, IonPage, IonRouterOutlet } from '@ionic/vue';
import { list, scan, person } from 'ionicons/icons';

export default defineComponent({
  name: 'TabsPage',
  components: { IonTabs, IonTabBar, IonTabButton, IonIcon, IonPage, IonRouterOutlet },
  setup() {
    return {
      list,
      scan,
      person
    }
  }
});
</script>

<style scoped>



ion-tabs {
  contain: none;
  z-index: 1;
}

ion-tab-bar {
  background-color: #ebebeb;
  height: 80px;
  border: none;
  contain: none
}

ion-tab-button {
  background-color: #ebebeb;
}

.side-tab ion-icon {
  background-color: #fff;
  padding: 12px;
  border-radius: 50%;
  font-size: 30px;
  margin: 0 !important;
  color: #000;
  border: 2px solid #48BF53;
}

ion-fab {
  transform: translateY(-40px);
}

ion-fab ion-icon {
  font-size: 34px;
}

ion-fab-button {
  --background: #48bf53;
  transform: scale(1.6);
}

</style>
