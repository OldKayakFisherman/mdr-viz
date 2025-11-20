<script setup lang="ts">
import SideMenu from './components/SideMenu.vue'
import SiteHeader from './components/SiteHeader.vue'

function handleMenuSelectionChange(index: number) {
  console.log(index)
}
</script>

<template>
  <v-app>
    <v-container>
      <v-row>
        <v-col>
          <SiteHeader @menu-selection-change="handleMenuSelectionChange" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <SideMenu />
        </v-col>
        <v-col> Body </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<style scoped></style>
