<template>
  <v-app>
    <v-navigation-drawer app v-model="drawer" clipped>
      <v-container>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="title grey--text text--darken-2">
              Nabigation Lists
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-divider></v-divider>
        <v-list nav>
          <v-list-group
            v-for="nav_list in nav_lists"
            :key="nav_list.name"
            :prepend-icon="nav_list.icon"
            no-action
            :append-icon="nav_list.lists ? undefined : ''"
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title>{{ nav_list.name }}</v-list-item-title>
              </v-list-item-content>
            </template>
            <v-list-item v-for="list in nav_list.lists" :key="list">
              <v-list-item-content>
                <v-list-item-title>{{ list }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
        </v-list>
      </v-container>
    </v-navigation-drawer>

    <v-app-bar color="primary" dark app clipped-left>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-items>
        <v-btn text to="/">Home<v-icon>mdi-home</v-icon></v-btn>
      </v-toolbar-items>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn text to="/about">About me</v-btn>
        <v-btn text to="/work">Work</v-btn>
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on" text>Contact<v-icon>mdi-menu-down</v-icon></v-btn>
          </template>
          <v-list>
            <v-subheader>SNS</v-subheader>
            <v-list-item v-for="support in supports" :key="support.name">
              <v-list-item-icon>
                <v-icon>{{ support.icon }}</v-icon>
                <v-list-item-content>
                  <v-list-item-title>{{ support.name }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item-icon>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar-items>
    </v-app-bar>
    <v-main>
      <router-view />
    </v-main>
    <v-footer color="primary" dark app height="100px">
      <v-row justify="center">
        <v-btn v-for="icon in icons" :key="icon" class="mx-5" dark icon>
          <v-icon size="30px">
            {{ icon }}
          </v-icon>
        </v-btn>
        <v-col class="primary lighten-2 py-4 text-center white--text" cols="12">
          {{ new Date().getFullYear() }} — <strong>（C)Wang.yu</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      supports: [
        { name: "Discord", icon: "mdi-discord" },
        { name: "Github", icon: "mdi-github" },
        { name: "Stack overflow", icon: "mdi-stack-overflow" },
        { name: "Twitter", icon: "mdi-twitter" },
        { name: "Contact form", icon: "mdi-email-outline" },
      ],
      nav_lists: [
        {
          name: "Home",
          icon: "mdi-home",
        },
        {
          name: "About me",
          icon: "mdi-baby-face",
        },
        {
          name: "Wrok",
          icon: "mdi-wrench",
        },
        {
          name: "Contact",
          icon: "mdi-qrcode",
          lists: [
            "Discord",
            "Github",
            "Stack overflow",
            "Twitter",
            "Contact form",
          ],
        },
      ],
      icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
    };
  },
};
</script>
