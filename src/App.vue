<template>
  <v-app id="inspire">
    <!-- <v-navigation-drawer v-model="drawer" app>
    </v-navigation-drawer> -->
    <v-navigation-drawer
      v-model="drawer"
      app
      dark
      src="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
      width="25%"
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Vue-Tudo-Vuetify
          </v-list-item-title>
          <v-list-item-subtitle>
            Lista de tarefas
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
      <v-list>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => {
    return {
      drawer: null,
      items: [
        { title: 'Tarefas', icon: 'mdi-view-dashboard', to: '/' },
        { title: 'Sobre', icon: 'mdi-image', to: '/about' }
      ],
      right: null
    }
  }
}
</script>
