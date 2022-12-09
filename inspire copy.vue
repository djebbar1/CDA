<template>

  <v-row justify="space-around">
    <v-col cols="auto">
      <v-dialog
        transition="dialog-bottom-transition"
        max-width="800"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Clinique</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Clinique</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="SIRET"
      :counter="10"
      :rules="SIRETRules"
      label="SIRET"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
      onclick="RedirectionJavascript()">

      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

    <!-- veterinaire -->

    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Vétérinaire</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Vétérinaire</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


    <!-- garde -->

    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="600"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Garde</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Garde</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="intervention"
      :rules="interventionRules"
      label="Intervention"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="commentaire"
      :rules="commentaireRules"
      label="Commentaire"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>

    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>




    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

<!-- Renseigement RDV-->

        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >RDV</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement RDV</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12">RDV</div>
              <div>
    <v-sheet
      tile
      height="54"
      class="d-flex"
    >
      <v-btn
        icon
        class="ma-2"
        @click="$refs.calendar.prev()"
      >
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
      <v-select
        v-model="type"
        :items="types"
        dense
        outlined
        hide-details
        class="ma-2"
        label="type"
      ></v-select>
      <v-select
        v-model="mode"
        :items="modes"
        dense
        outlined
        hide-details
        label="event-overlap-mode"
        class="ma-2"
      ></v-select>
      <v-select
        v-model="weekday"
        :items="weekdays"
        dense
        outlined
        hide-details
        label="weekdays"
        class="ma-2"
      ></v-select>
      <v-spacer></v-spacer>
      <v-btn
        icon
        class="ma-2"
        @click="$refs.calendar.next()"
      >
        <v-icon>mdi-chevron-right</v-icon>
      </v-btn>
    </v-sheet>
    <v-sheet height="600">
      <v-calendar
        ref="calendar"
        v-model="value"
        :weekdays="weekday"
        :type="type"
        :events="events"
        :event-overlap-mode="mode"
        :event-overlap-threshold="30"
        :event-color="getEventColor"
        @change="getEvents"
      ></v-calendar>
    </v-sheet>
  </div>
  <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
    <!--  -->

    <!--  -->
      </v-dialog>
    </v-col>



<!-- Préscription  -->
    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>
<!--  -->

    <!--  -->
    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

    <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Client</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Client</v-toolbar>
            <v-card-text>
              <div class=" text-center text-h2 pa-12 " >Client</div>
              <v-form
            ref="form"
            v-model="valid"
            lazy-validation
        >
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-select
      v-model="select"
      :items="items"
      :rules="[v => !!v || 'Item is required']"
      label="Animaux"
      required

    ></v-select>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>
  </v-form>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!--  -->


<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>



    <!-- -->

    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

  <!--  -->
  <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


<!-- -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


    <!--  -->

    <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


  <!--  -->

  <v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!-- -->
<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!--  -->
<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>

<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


<!--  -->

<!--  -->

<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>



<!-- -->
<v-col cols="auto">
      <v-dialog
        transition="dialog-top-transition"
        max-width="800"
      >

      <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Préscription</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar
              color="primary"
              dark
            >Renseignement Préscription</v-toolbar>
            <v-card-text>
              <div class="text-h2 pa-12"></div>
              <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="lastname"
      :counter="10"
      :rules="lastnameRules"
      label="LastName"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
      <v-text-field
      v-model="firstname"
      :counter="10"
      :rules="firstnameRules"
      label="FirstName"
      required
      width="60px"
    ></v-text-field>
    </div>
  </v-row>
  <v-row class="justify-space-around" >
    <div>
    <v-text-field
      v-model="Adress"
      :rules="AdressRules"
      label="Adress"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="CodePostal"
      :rules="CodePostalRules"
      label="Code Postal"
      required
      width="60px"
    ></v-text-field>
    </div>

  </v-row>
  <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="Telephone"
      :rules="TelephoneRules"
      label="Telephone"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
      width="60px"
    ></v-text-field>
    </div>

    </v-row>
    <v-row width="60px" class="justify-space-around" >
    <div width="60px">
    <v-text-field
      v-model="assurance"
      :rules="assuranceRules"
      label="Assurance"
      required
      width="60px"
    ></v-text-field>
    </div>
    <div>
    <v-text-field
      v-model="date"
      :rules="dateRules"
      label="Date"
      required
      width="60px"
    ></v-text-field>
    </div>
    </v-row>

    <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue!']"
      label="Do you agree?"
      required
    ></v-checkbox>

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
      Validate
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

    <v-btn
      color="warning"
      @click="resetValidation"
    >
      Reset Validation
    </v-btn>

            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn
                text
                @click="dialog.value = false"
              >Close</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>


  </v-row>
</template>
<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      select: null,
      items: [
        'Chien',
        'Chat',
        'Oiseau',
        'reptile',
        'Autre',
      ],
      checkbox: false,

      type: 'month',
      types: ['month', 'week', 'day', '4day'],
      mode: 'stack',
      modes: ['stack', 'column'],
      weekday: [0, 1, 2, 3, 4, 5, 6],
      weekdays: [
        { text: 'Sun - Sat', value: [0, 1, 2, 3, 4, 5, 6] },
        { text: 'Mon - Sun', value: [1, 2, 3, 4, 5, 6, 0] },
        { text: 'Mon - Fri', value: [1, 2, 3, 4, 5] },
        { text: 'Mon, Wed, Fri', value: [1, 3, 5] },
      ],
      value: '',
      events: [],
      colors: ['blue', 'indigo', 'deep-purple', 'cyan', 'green', 'orange', 'grey darken-1'],
      names: ['Meeting', 'Holiday', 'PTO', 'Travel', 'Event', 'Birthday', 'Conference', 'Party'],

    }),

    methods: {
      validate () {
        this.$refs.form.validate()
        function RedirectionJavascript(){
          document.location.href="conn_client.vue";
          }
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },

      getEvents ({ start, end }) {
        const events = []

        const min = new Date(`${start.date}T00:00:00`)
        const max = new Date(`${end.date}T23:59:59`)
        const days = (max.getTime() - min.getTime()) / 86400000
        const eventCount = this.rnd(days, days + 20)

        for (let i = 0; i < eventCount; i++) {
          const allDay = this.rnd(0, 3) === 0
          const firstTimestamp = this.rnd(min.getTime(), max.getTime())
          const first = new Date(firstTimestamp - (firstTimestamp % 900000))
          const secondTimestamp = this.rnd(2, allDay ? 288 : 8) * 900000
          const second = new Date(first.getTime() + secondTimestamp)

          events.push({
            name: this.names[this.rnd(0, this.names.length - 1)],
            start: first,
            end: second,
            color: this.colors[this.rnd(0, this.colors.length - 1)],
            timed: !allDay,
          })
        }

        this.events = events
      },
      getEventColor (event) {
        return event.color
      },
      rnd (a, b) {
        return Math.floor((b - a + 1) * Math.random()) + a
      },
    },
  }
</script>
