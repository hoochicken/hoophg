<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Hoochicken Photo Gallery</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 2</ion-title>
        </ion-toolbar>
      </ion-header>

      <!--ExploreContainer name="Tab 2 page" /-->
      <ion-content :fullscreen="true">
        <ion-fab vertical="bottom" horizontal="center" slot="fixed">
          <ion-fab-button @click="takePhoto()">
            <ion-icon :icon="camera"></ion-icon>
          </ion-fab-button>
        </ion-fab>
      </ion-content>
    </ion-content>

    <ion-content>
      <ion-grid>
        <ion-row>
          <ion-col size="6" :key="photo" v-for="photo in photos">
            <ion-img :src="photo.webviewPath"></ion-img>
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-content>
  </ion-page>
</template>


<script lang="ts">
import { camera, trash, close } from 'ionicons/icons';
import { IonPage, IonHeader, IonFab, IonFabButton, IonIcon,
  IonToolbar, IonTitle, IonContent, IonGrid, IonRow,
  IonCol, IonImg } from '@ionic/vue';
import { usePhotoGallery, Photo } from '@/composables/usePhotoGallery';

export default  {
  name: 'Tab2',
  components: { IonPage, IonHeader, IonFab, IonFabButton, IonIcon,
    IonToolbar, IonTitle, IonContent, IonGrid, IonRow,
    IonCol, IonImg },
  setup() {
    const { photos, takePhoto } = usePhotoGallery();

    return {
      photos,
      takePhoto,
      camera, trash, close
    }
  }
}
</script>

<!--script lang="ts">
// import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
// import ExploreContainer from '@/components/ExploreContainer.vue';

import { camera, trash, close } from 'ionicons/icons';
import { IonPage, IonHeader, IonFab, IonFabButton, IonIcon,
  IonToolbar, IonTitle, IonContent, IonGrid, IonRow,
  IonCol, IonImg } from '@ionic/vue';
import { usePhotoGallery } from '@/composables/usePhotoGallery';

export default  {
  name: 'Tab2',
  // components: { ExploreContainer, IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
  // components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
  components: { IonPage, IonHeader, IonFab, IonFabButton, IonIcon,
    IonToolbar, IonTitle, IonContent, IonGrid, IonRow,
    IonCol, IonImg },
  setup() {
    const { takePhoto } = usePhotoGallery();
    return {
      takePhoto,
      camera, trash, close
    }
  }
}
</script-->
