<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Rechercher</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large" class="title_color">Rechercher un véhicule</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-item class="item">
        <ion-label position="floating" class="radius color_label">Rechercher un véhicule</ion-label>
        <ion-input type="text" v-model="name" class="input"></ion-input>
      </ion-item>
      <ion-button color="primary" @click="search">Rechercher</ion-button>

      <table>
        <th>Commande N°</th>
        <th>Véhicule</th>
        <tr>
          <td>E15486</td>
          <td>Alfa Roméo Mito</td>
        </tr>
      </table>
    </ion-content>
  </ion-page>
</template>

<script>
import {defineComponent, ref} from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonItem, IonLabel, IonInput, IonButton } from '@ionic/vue';


export default defineComponent({
  name: 'Tab2Page',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonItem, IonLabel, IonInput, IonButton },
  setup() {
    let users = ref([])
    let name = ref('')

    const addUser = () => {
      users.value.push({
        name: name.value,
        score: 0
      })

      name.value = ''
    }

    const resetUser = () => {
      users.value = []
    }

    return {users, name, addUser, resetUser}
  }
});
</script>
