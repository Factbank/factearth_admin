<template>
  <v-list-tile @click="redirectTo">
    <v-list-tile-action>
      <v-icon>{{ icon }}</v-icon>
    </v-list-tile-action>
    <v-list-tile-content>
      <v-list-tile-title>{{ title }}</v-list-tile-title>
    </v-list-tile-content>
  </v-list-tile>
</template>

<script>
export default {
  methods: {
    redirectTo() {
      this.$router.push({ path: this.link })
    }
  },
  props: ['link', 'title', 'icon']
}
</script>

<style lang="scss" scoped>
i.v-icon.material-icons.theme--light {
  color: #d64113;
}
</style>
