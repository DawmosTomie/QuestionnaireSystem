<template>
  <v-menu left>
    <template v-slot:activator="{ on: menu }">
    <div class="fixed-button">
      <v-tooltip left>
        <template v-slot:activator="{ on: tooltip }">
          <v-btn
            icon
            v-on="{ ...tooltip, ...menu }"
            v-show="$viewport .width > 450">
            <v-icon>mdi-help-circle</v-icon>
          </v-btn>
        </template>
        <span class="tooltip">Help & feedback</span>
      </v-tooltip>
    </div>
    </template>

    <v-list>
      <v-list-item
        v-for="(item, index) in items"
        :key="index"
        @click="">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-title>{{ item.name }}</v-list-item-title>
      </v-list-item>
    </v-list>

  </v-menu>
</template>

<script>
  export default {
    data() {
      return {
        items: [
          { name: 'Take a tour', icon: 'mdi-star'},
          { name: 'Report a problem', icon: 'mdi-message-alert'},
          { name: 'Help Center', icon: 'mdi-help-circle'},
          { name: 'Back to the old Forms', icon: 'mdi-exit-run'},
        ]
      }
    }
  }
</script>

<style scoped>
  .fixed-button {
    position: fixed;
    font-size: 1px;
    bottom: 1px;
    right: 1px;
  }
</style>
