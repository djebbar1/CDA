<template>

<v-container id="cc">
  <v-img src="https://fr.freepik.com/vecteurs-libre/ensemble-animaux-sauvages_4613359.htm#query=animaux%20sauvages&position=1&from_view=keyword"></v-img>
  <div id="bo">
        <div id="lav" class="text-center">
            <h1>Logiciel de gestion d'animaux</h1>
            <h2>Nos amies les bêtes</h2>

        </div>
        <div id="la">
      <label for="name">Code Administratif</label>
      <input type="password" id="connexion_admin" name="code" required minlength="4" maxlength="8" size="10" OnClick="window.location.href='page_clin.php'">

    </div>


  <v-row>
    <v-col>
      <v-card
    class="mx-auto pl-auto"
    max-width="500"
    height="200"
    outlined
  >
    <h2 id="lavv" class="text-center">Espace Professionnelle</h2>

    <div>
    <v-card-actions  id="pos" class="text-overline mb-4">


  <v-row justify="center">
    <v-dialog
      v-model="dialog_Admin"
      persistent
      max-width="600px"
    >
      <template v-slot:activator="{ on, attrs }">

        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Connexion
        </v-btn>

      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">User Profile</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  label="Email*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Password*"
                  type="password"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="blue darken-1"
            text
            @click="dialog_Admin = false"
          >
            Annulé
          </v-btn>
          <v-btn
            color="blue darken-1"
            text
            @click="dialog_Admin = false"
            onclick="document.location.href='http://localhost:3000/inscrip_clinique'"
          >
            Connexion
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>

</v-card-actions>
</div>
</v-card>
<v-card
  class="mx-auto pl-auto"
  max-width="500"
  height="200"
  outlined
>
      <div id="lavv" class="text-h mb-1">
        <h2 id="lavv" class="text-center">Espace Client</h2>
      </div>
  <div >
    <v-card-actions id="pos">


  <v-row justify="center">
    <v-dialog
      v-model="dialog_client"
      persistent
      max-width="600px"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Connexion
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5-center">Profile client</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  label="Email*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Password*"
                  type="password"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions id="lavv">
          <v-spacer></v-spacer>
          <v-btn
            color="blue darken-1"
            text
            @click="dialog_client = false"
          >
            Annulé
          </v-btn>
          <v-btn
            color="blue darken-1"
            text
            @click="dialog_client = false"
            onclick="document.location.href='http://localhost:3000/carnet'"
          >
            Connexion
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>

    </v-card-actions>
  </div>
  </v-card>

</v-col>
</v-row>
</div>

  <!-- const db = pgadmin4.createConnection({   host: "localhost",   user: "connexion_admin",   password: "code" });-->
</v-container>
</template>


<script type="module">
  // Import the functions you need from the SDKs you need
  //import { initializeApp } from "https://www.gstatic.com/firebasejs/9.14.0/firebase-app.js";
  // TODO: Add SDKs for Firebase products that you want to use
  // https://firebase.google.com/docs/web/setup#available-libraries

  // Your web app's Firebase configuration
  const firebaseConfig = {
    apiKey: "AIzaSyAter14Gg6a4-yBnjlyMw-5OrXMOlvUIIk",
    authDomain: "blog-aab0f.firebaseapp.com",
    projectId: "blog-aab0f",
    storageBucket: "blog-aab0f.appspot.com",
    messagingSenderId: "493001906808",
    appId: "1:493001906808:web:0cb6cc87f633f719866b8d"
  };

  // Initialize Firebase
 // const app = initializeApp(firebaseConfig);

export default {
  valid: true,
  name: 'Accueil',
  data () {
    return{
      dialog_clinique:false,
      dialog_client: false,
      dialog_Admin: false,
      code: '12345678',
      data: null,
      connected: 'false',
      identifiant: null,
      mdp: null,
      defaultUser: 'Thomas',
      defaultMdp: 'Toto123',
      erreur: false,
      erreurMdp: false,
      menu: false,
      erreurIdentifiant: false,

      connexion_adminRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      code: 'code',
      codeRules: [
        v => !!v || 'code is required',
        v => /.+@.+\..+/.test(v) || 'code must be valid',
      ],
      value: '123456',
      events: [],
      colors: ['blue', 'indigo', 'deep-purple', 'cyan', 'green', 'orange', 'grey darken-1'],
      names: ['Meeting', 'Holiday', 'PTO', 'Travel', 'Event', 'Birthday', 'Conference', 'Party'],


    }

  },

    methods: {

    deconnexion(){
         localStorage.setItem('connected', false)
         localStorage.setItem('identifiant', null)
         this.connected = false
         console.log('déconnexion')
         //this.$router.replace({ path: 'inspire'})
    },
     connexion() {
        this.$fire.firestore.collection('users').doc(this.identifiant).get().then(doc => {
          if(doc.exists){
            this.erreurIdentifiant = false
            this.defaultMdp = doc.data().pass

            if(this.mdp.length < 6){
                this.erreurMdp = true
                return
            }
        if(this.mdp === this.defaultMdp){
          this.menu = false
          localStorage.setItem('identifiant', this.identifiant)
          localStorage.setItem('connected', true)
          this.erreur = false
          this.erreurMdp = false
          this.connected = true
        } else {
          this.erreurMdp = false
          this.erreur = true
          this.connected = false
         localStorage.setItem('identifiant', null)
          localStorage.setItem('connected', false)
        }
          } else {
            this.erreurIdentifiant = true
          }

        })
    },
  },
}
</script>
<style>
  #pos {
  justify-content: flex-end;
}
#bo{
  position: absolute;
  top:50%;
  left: 50%;
  transform: translate(-50% , -50%);
}
#lav{

    margin: 30px;
}
#lavv{

margin: 30px;
}
#av{
  display: float;
  float: right;
}

</style>
