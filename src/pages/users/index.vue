<template>
  <v-data-table
    :headers="headers"
    :items="users"
    hide-actions
    class="elevation-1"
  >
    <template slot="items" slot-scope="props">
      <td>{{ props.item.name }}</td>
      <td class="text-xs-right">{{ props.item.email }}</td>
      <td class="text-xs-right">{{ props.item.logins }}</td>
      <td class="text-xs-right">{{ props.item.reports }}</td>
      <td class="text-xs-right"><v-btn color="info">ユーザーページ</v-btn><v-btn color="error">アカウント無効化</v-btn></td>
    </template>
  </v-data-table>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: 'Name',
          align: 'left',
          sortable: false,
          value: 'Name'
        },
        { text: 'Email', value: 'email' },
        { text: 'login count', value: 'logins' },
        { text: '通報回数', value: 'reports' },
        { text: 'アクション', value: 'action' }
      ],
      users: [
        {
          value: false,
          name: 'Frozen Yogurt',
          email: 6.0,
          logins: 24,
          reports: 4.0
        },
        {
          value: false,
          name: 'Ice cream sandwich',
          email: 9.0,
          logins: 37,
          reports: 4.3
        },
        {
          value: false,
          name: 'Eclair',
          email: 16.0,
          logins: 23,
          reports: 6.0
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.layout {
  display: inline-block;
  width: 100%;
}
</style>
