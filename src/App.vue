<template>
  <v-app>

    <v-main>
      <v-toolbar class="mb-4 hidden-xs-only purple" >
        <v-app-bar-nav-icon @click="asideSwitcher" class="white--text" />
        <v-toolbar-title class=" d-flex" style="width: 100%"  >
           <span class="white--text">Title</span>
           <span class="white--text">Text</span>
          <v-spacer></v-spacer>
        </v-toolbar-title>
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on"> Menu </v-btn>
          </template>

          <v-list>
            <v-list-item v-for="item in items" :key="item.id" exact :to="item.path">
              <v-list-item-title>{{item.path}}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>

        <v-dialog >
          <template v-slot:activator="{on}">
            <v-btn class="ml-2" v-on="on">Dialog(popup)</v-btn>
          </template>
          <v-card>
            <v-card-title>
              blblba
            </v-card-title>
          </v-card>
        </v-dialog>
      </v-toolbar>


     <router-view></router-view>




    </v-main>
    <v-navigation-drawer  app v-model="aside">
      <v-container>
        <v-row >
          <v-col col="12" class="text-center">
            <v-avatar rounded="circle" >
              <img src="https://www.fillmurray.com/100/100" alt="">
            </v-avatar>
          </v-col>
        </v-row>
      </v-container>
      <v-list nav>
        <v-list-item-group>
          <v-list-item v-for="item in items" :key="item.id"  exact :to="item.path">
            <v-list-item-icon>
              <v-icon >mdi-email</v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              {{item.path}}
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>

export default {

  data: () => ({
    aside: false,
    items: [
      {id: 1, path: '/'},
      {id: 2, path: '/about'},
    ]
  }),
  methods: {
    asideSwitcher() {
      this.aside = !this.aside
    },
    sayHi() {
      alert(this.hiMsg)
    }
  }
};
</script>
