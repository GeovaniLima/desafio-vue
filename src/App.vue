<template>
  <v-app id="inspire">
      <v-card>
        <v-navigation-drawer
          app
          v-model="drawer"
          :mini-variant.sync="mini"
          permanent
        >
          <v-list-item class="px-2">
            <v-list-item-avatar>
              <v-img src="https://avatars.githubusercontent.com/u/66522839?v=4"></v-img>
            </v-list-item-avatar>

            <v-list-item-title>Geovani Lima</v-list-item-title>

            <v-btn
              icon
              @click.stop="mini = !mini"
            >
              <v-icon>mdi-chevron-left</v-icon>
            </v-btn>
          </v-list-item>

          <v-divider></v-divider>

          <v-list dense>
            <v-list-item
              v-for="item in items"
              :key="item.title"
              link
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
      </v-card>

    <v-app-bar
      app
      color="#00335F"
      dark
    >
      <v-app-bar-title>HAP Engenharia</v-app-bar-title>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

  export default {
    name: 'App',

    data () {
      return {
        drawer: true,
        items: [
          { title: 'Home', icon: 'mdi-home-city' },
          { title: 'Minha Conta', icon: 'mdi-account' },
          { title: 'Usuários', icon: 'mdi-account-group-outline' },
        ],
        mini: true,
      }
    },
  };

</script>
