<template>
  <nav>
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Store Locator
          </v-list-item-title>
          <v-list-item-subtitle>
            Nuxt Project
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider />

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
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
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>Page Title</v-toolbar-title>
    </v-app-bar>
  </nav>
</template>

<script>
export default {
  name: 'SideNavigation',
  data: () => ({
    drawer: false,
    items: [
      { title: 'Dashboard', icon: 'mdi-view-dashboard', to: '/' },
      { title: 'Inbox', icon: 'mdi-email', to: '/inbox' },
      { title: 'Store Finder', icon: 'mdi-format-list-bulleted-square', to: '/store-list-map' },
      { title: 'About', icon: 'mdi-help-box', to: '/about' }
    ],
    right: null
  })
}
</script>

<style scoped>

</style>
