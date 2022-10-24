<template>
  <v-app dark>
    <v-navigation-drawer permanent :mini-variant="miniVariant" app style="background-color:#3d323e">
      <v-list class="pa-0">
        <v-list-item
          style="cursor: pointer"
          @click.stop="miniVariant = !miniVariant"
        >
          <v-list-item-action>
            <v-icon
              >mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon
            >
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title> {{ title }} </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer padless inset app :absolute="False" style="background-color:#594959">
      <v-col class="text-center"
        >&copy; {{ new Date().getFullYear() + ' ' + copyright }}
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      items: [
        {
          icon: 'mdi-home',
          title: 'Home',
          to: '/',
        },{
          icon: 'mdi-account',
          title: 'About',
          to: '/about',
        },{
          icon: 'mdi-brush',
          title: 'Projects',
          to: '/projects',
        },
        {
          icon: 'mdi-email',
          title: 'Contact',
          to: '/contact',
        },
      ],
      miniVariant: true,
      title: ' ',
      copyright: 'Ariane Van der Haegen',
    }
  },
}
</script>

<style>
html {
  overflow-y: auto;
}
</style>
