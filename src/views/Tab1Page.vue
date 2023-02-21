<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Connexion</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large" class="title_color">Connexion</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-item class="item">
        <ion-label position="floating" class="radius color_label">Email</ion-label>
        <ion-input type="text" v-model="email" class="input"></ion-input>
        <ion-label position="floating" class="color_label">Mot de passe</ion-label>
        <ion-input type="password" v-model="password" class="input"></ion-input>
      </ion-item>
      <ion-button color="primary" @click="addUser">Se connecter</ion-button>

      <div id="list__users">
        <user-card v-for="(user, index) in users" :key="index" :name="user.name" :score="user.score"/>
      </div>
    </ion-content>
  </ion-page>
</template>

<script>
import {defineComponent, ref} from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonItem, IonLabel, IonInput, IonButton } from '@ionic/vue';
import UserCard from "@/components/UserCard";

export default defineComponent({
  name: 'Tab2Page',
  components: { IonHeader, IonToolbar, IonTitle, IonContent, IonPage, IonItem, IonLabel, IonInput, IonButton, UserCard },
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
