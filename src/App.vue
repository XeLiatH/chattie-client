<template>
  <v-app>

<!--    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Releaseee</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>-->

    <v-navigation-drawer
        app
        permanent
    >
      <template v-slot:prepend>
        <v-list-item two-line>
          <v-list-item-avatar>
            <img src="https://randomuser.me/api/portraits/women/81.jpg">
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>Jane Smith</v-list-item-title>
            <v-list-item-subtitle>Logged In</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </template>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
            v-for="item in items"
            :key="item.title"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container class="d-flex flex-column-reverse" style="height: 100%;">

        <div class="d-flex align-baseline">
          <v-text-field
              label="Main input"
              hide-details="auto"
          ></v-text-field>
          <v-btn class="ml-5" color="primary">Send</v-btn>
        </div>

        <v-row>
          <v-col class="d-inline-flex flex-column-reverse">
            <v-row class="flex-grow-0">
              <v-col class="text-left">
              </v-col>
              <v-col class="text-right">
                <v-card elevation="0">
                  <v-card-text class="py-0">
                    <div class="text--primary">
                      <v-tooltip left>
                        <template v-slot:activator="{ on, attrs }">
                          <v-chip v-bind="attrs" v-on="on">Yo dude</v-chip>
                        </template>
                        <span>15:20</span>
                      </v-tooltip>
                    </div>
                  </v-card-text>
                </v-card>
              </v-col>
            </v-row>

            <v-row  class="flex-grow-0">
              <v-col class="text-left">
                <v-tooltip right>
                  <template v-slot:activator="{ on, attrs }">
                    <v-chip v-bind="attrs" v-on="on">Yo dude</v-chip>
                  </template>
                  <span>15:20</span>
                </v-tooltip>
              </v-col>
              <v-col class="text-right">
              </v-col>
            </v-row>
          </v-col>
        </v-row>

      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import io from 'socket.io-client';

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    socket: io('http://localhost:8888'),
    items: [
      { title: 'Home', icon: 'mdi-home-city' },
      { title: 'My Account', icon: 'mdi-account' },
      { title: 'Users', icon: 'mdi-account-group-outline' },
    ],
  }),
};
</script>
