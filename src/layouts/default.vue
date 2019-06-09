<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" class="hidden-sm-and-up" fixed disable-resize-watcher width="200">
      <v-list>
        <v-list-tile v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed app color="primary">
      <v-toolbar-side-icon class="hidden-sm-and-up" aria-label="Hamburger Menu Button" @click="drawer = !drawer" />
      <v-toolbar-title>
        <nuxt-link to="/">{{ title }}</nuxt-link>
      </v-toolbar-title>
      <v-spacer />
      <v-toolbar-items class="hidden-xs-only">
        <v-btn v-for="(item, i) in items" :key="i" flat :to="item.to" router>{{ item.title }}</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <v-container fill-height>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer fixed app color="primary">
      <v-layout justify-center>
        <span>&copy; 2019 yuki</span>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      title: `Yuki's Portfolio`,
      items: [
        {
          icon: 'perm_identity',
          title: 'Profile',
          to: '/profile'
        },
        {
          icon: 'history',
          title: 'History',
          to: '/history'
        }
      ],
      drawer: false
    }
  }
}
</script>

<style>
.v-toolbar__title a {
  color: black;
  text-decoration: none;
}
</style>
