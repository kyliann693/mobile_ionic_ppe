<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Commande</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Commande</ion-title>
        </ion-toolbar>
      </ion-header>
      <p>Choisissez une agence afin de sélectionner un véhicule</p>
      <ion-item>
        
        <ion-label position="floating" class="radius color_label">Nom</ion-label>
        <ion-input type="text" v-model="name" class="input"></ion-input>
        <ion-label position="floating" class="color_label">Prénom</ion-label>
        <ion-input type="text" v-model="firstname" class="input"></ion-input>
        <ion-label position="floating" class="color_label">Email</ion-label>
        <ion-input type="mail" v-model="mail" class="input"></ion-input>
        <ion-label position="floating" class="color_label">Début</ion-label>
        <ion-input type="date" v-model="start" class="input"></ion-input>
        <ion-label position="floating" class="color_label">Fin</ion-label>
        <ion-input type="date" v-model="stop" class="input"></ion-input>
      
        <table>
          <th>Agence disponible</th>
          <th>Véhicules</th>
          <tr>
              <select v-model="agence">
                <option>Agence</option>
                <option>Agence 1</option>
              </select>
            <td>
              <select  v-model="car">
                <option>Véhicule</option>
                <option>Alfa Roméo MiTo</option>
              </select>
            </td>
          </tr>
        </table>
      </ion-item>
      <div id="button_block">
        <div id="center_button">
          <ion-button color="primary" @click="addCommande" class="command_button">Commander</ion-button>
        </div>
      </div>
      <div id="list__users">
        <user-card v-for="(user, index) in users" :key="index" :name="user.agence" :car="user.car"/>
      </div>    
    </ion-content>
   
  </ion-page>
</template>

<script>
import {defineComponent, ref} from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonItem, IonButton } from '@ionic/vue';
import UserCard from "@/components/UserCard";

export default defineComponent({
  name: 'Tab2Page',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonItem, IonButton, UserCard },
  setup() {
    let users = ref([])
    let agence = ref('')
    let car = ref('')

    const addCommande = () => {
      users.value.push({
        agence: agence.value,
        car: car.value
      })

      agence.value = ''
      car.value = ''
    }

    const resetUser = () => {
      users.value = []
    }

    return {users, agence, car, addCommande, resetUser}
  }
});

  
</script>
