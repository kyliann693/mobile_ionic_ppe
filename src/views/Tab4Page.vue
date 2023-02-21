<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Historique des commandes</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Historique des commandes</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-item>

        <table>
          <th>Commande N°</th>
          <th>Véhicules</th>
          <tr>
            <td>E15486</td>
            <td>Alfa Roméo Mito</td>
          </tr>
        </table>
      </ion-item>
      <div id="list__users">
        <user-card v-for="(user, index) in users" :key="index" :name="user.name" :score="user.score"/>
      </div>
    </ion-content>
  


  </ion-page>
</template>

<script>
import {defineComponent} from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonItem } from '@ionic/vue';

export default defineComponent({
  name: 'Tab3Page',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonItem },
 
 
});
</script>

<style scoped>
#list__cities div {
  padding: 10px;
  background: #d4d4d4;
  border-radius: 8px;
  margin: 5px;
  color: #282828
}
</style>


