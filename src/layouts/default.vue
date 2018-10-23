<template>
  <v-app>
    <v-navigation-drawer app v-model='isDrawerOpen'>
      <v-list dense>
        <App-drawer v-for="(drawer, key) in drawerList" :key="key" :title="drawer.title" :icon="drawer.icon" :link="drawer.link"><v-divider/></App-drawer>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar color="#D64113" dark fixed app>
      <v-toolbar-side-icon @click.stop="isDrawerOpen = !isDrawerOpen"></v-toolbar-side-icon>
      <v-toolbar-title><router-link to='/'>Factearth Admin</router-link></v-toolbar-title>
    </v-toolbar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout>
          <router-view/>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import AppDrawer from '@/components/AppDrawer.vue'

export default {
  data() {
    return {
      isDrawerOpen: null,
      drawerList: [
        {
          link: '/',
          title: 'Home',
          icon: 'home'
        },
        {
          link: '/users/',
          title: 'ユーザー管理',
          icon: 'account_circle'
        },
        {
          link: '',
          title: 'ガイド管理',
          icon: 'airplanemode_active'
        },
        {
          link: '',
          title: '入金管理',
          icon: 'attach_money'
        },
        {
          link: '',
          title: 'お問い合わせ管理',
          icon: 'contact_mail'
        }
      ]
    }
  },
  components: { AppDrawer }
}
</script>

<style>
a.router-link-active {
  color: #fff;
  text-decoration: none;
}
</style>
