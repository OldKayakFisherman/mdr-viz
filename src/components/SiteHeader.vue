<script setup lang="ts">
const emit = defineEmits(['menuSelectionChange'])

const menuitems = [{ title: 'Data' }, { title: 'Reports' }, { title: 'Search' }]

function handleSelectionChange(key: number) {
  emit('menuSelectionChange', key)
}
</script>

<template>
  <v-toolbar class="text-white" image="./images/header.jpg">
    <v-menu open-on-hover>
      <template v-slot:activator="{ props }">
        <v-btn icon="mdi-menu" v-bind="props"></v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in menuitems"
          :key="index"
          :value="index"
          @click="handleSelectionChange(index)"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>

    <v-toolbar-title text="MDR Data Analysis"></v-toolbar-title>

    <v-btn icon="mdi-export"></v-btn>
  </v-toolbar>
</template>
