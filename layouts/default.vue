<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>

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
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon id="drawerr" @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">

        <v-icon id="mdii">mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title id="titlee">{{ title }}</v-toolbar-title>
      <v-spacer />
    </v-app-bar>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ footerr }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      footerr: 'Design Firdes Beyzanur',
      items: [
        {
          icon: 'mdi-apps',
          title: 'Random Number',
          to: '/'
        },
        {
          icon: 'mdi-apps',
          title: 'Interger Random Number',
          to: '/interger'
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'My WebSite'
    }
  }
}
</script>

<style scoped>
#titlee {
  color: rgb(124, 163, 127);
}

#drawerr {
  color: rgb(124, 163, 127);
}

#mdii {
  color: rgb(124, 163, 127);
}
</style>