<template>
  <div class="about">
    <v-snackbar class="" v-model="snackbar" timeout="1000" top color="success">
      <p>blabla</p>
    </v-snackbar>
    <v-container>
      <v-row>
        <v-col cols="12">
          <p class="text-h3">Accordeon</p>
        </v-col>
        <v-col cols="12">
          <v-expansion-panels>
            <v-expansion-panel class="mt-0">
              <v-expansion-panel-header>Heading</v-expansion-panel-header>
              <v-expansion-panel-content class="purple white--text pt-3" >
                <p class="mb-0">blabla</p>
              </v-expansion-panel-content>
            </v-expansion-panel >
            <v-expansion-panel class="mt-0">
              <v-expansion-panel-header>Heading</v-expansion-panel-header>
              <v-expansion-panel-content class="purple white--text pt-3" >
                <p class="mb-0">blabla</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel class="mt-0">
              <v-expansion-panel-header>Heading</v-expansion-panel-header>
              <v-expansion-panel-content class="purple white--text pt-3" >
                <p class="mb-0">blabla</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
            <v-expansion-panel class="mt-0">
              <v-expansion-panel-header>Heading</v-expansion-panel-header>
              <v-expansion-panel-content class="purple white--text pt-3" >
                <p class="mb-0">blabla</p>
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>
      </v-row>
      <v-row class="mt-5">
        <v-col cols="12">
          <p class="text-h3">Datepicker</p>
        </v-col>
        <v-col>
          <v-menu offset-y>
            <template v-slot:activator="{ on }">
              <v-btn v-on="on"  class="success white--text">Click me</v-btn>
            </template>
            <v-date-picker  v-model="picker" color="green lighten-1"></v-date-picker>
          </v-menu>
        </v-col>
      </v-row>
      <v-row class="mt-5">
        <v-col cols="12">
          <p class="text-h3">Form, inputs, validation</p>
        </v-col>
        <v-col>
          <v-form ref="form">
            <v-text-field
                label="label text"
                color="purple"
                prepend-icon="mdi-folder"
                :rules="validationRules"
                v-model="input"
            >
            </v-text-field>
            <v-textarea
                label="textarea label"
                color="purple"
                :rules="validationRules"
                v-model="textArea"
            >

            </v-textarea>
            <v-btn :loading="false" class="mt-5" @click="submit">Submit form</v-btn>
            <v-btn :loading="true" class="mt-5" @click="submit">:loading=true</v-btn>
          </v-form>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-btn class="indigo darken-1 white--text" @click="snackbar = !snackbar">Show Snackbar</v-btn>
        </v-col>
      </v-row>

    </v-container>
  </div>



</template>
<script>
export  default {
  data() {
    return {
      //байндится на инпут и срабатывает каждый раз при вводе
      validationRules: [
          value => value.length >= 3 || 'Value must be 3 or more characters'
      ],
      picker: new Date().toISOString().substr(0, 10),
      input: '',
      textArea: '',
      snackbar: false
    }
  },
  methods: {
    submit() {
      if(this.$refs.form.validate()) { //ф-я запускающая валидацию
        //если валидно - пушим на бэк, если нет - автоматом подсвечиваются ошибки
        console.log(this.input, this.textArea)
      }
    }
  }
}

</script>