<template>
  <div class="home">
    <v-container>
      <v-row class="purple"  justify="space-between">
        <v-col sm="12" md="4">
          <p class="red white--text py-2 px-4 text-center">Home</p>
        </v-col>
        <v-col sm="12" md="4">
          <v-btn block>Btn</v-btn>
        </v-col>
      </v-row>
      <v-row>
        <v-col md="12" class="text-right" >
          <v-tooltip bottom >
            <template v-slot:activator="{on}">
              <v-chip class="yellow black--text " v-on="on" >
                blabla chip
              </v-chip>
            </template>

            <span>Some tooltip text</span>
          </v-tooltip>
          <v-card class="text-center pa-3">

            <v-avatar class="grey" rounded="circle" size="100">
              <img src="https://www.fillmurray.com/100/100" alt="" />
            </v-avatar>
          </v-card>
        </v-col>

      </v-row>
    </v-container>

  </div>
</template>
<script>
export  default {

}

</script>