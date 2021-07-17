<template>
  <div>
    <v-app-bar app class="warning">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Vuetify-Maps</v-toolbar-title>
      
      <v-spacer></v-spacer>
      <Notifications />
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute bottom temporary dark>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Menu </v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link :to="item.to">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
import Notifications from "./Notifications.vue";
export default {
  components: {
    Notifications,
  },
  data: () => ({
    drawer: false,
    items: [
      { title: "Inicio", icon: "home", to: "/" },
      { title: "Mapa", icon: "location_on", to: "/Maps" },
      { title: "Acerca", icon: "contact_support", to: "/About" },
    ],
  }),
};
</script>

