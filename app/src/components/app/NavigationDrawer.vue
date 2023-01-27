<script setup lang="ts">
  // params
  const navs: {
    prependIcon: string;
    title: string;
    value: string;
    to: string;
  }[] = [
    {
      prependIcon: 'mdi-home',
      title: 'Home',
      value: 'home',
      to: '/',
    },
    {
      prependIcon: 'mdi-information',
      title: 'About',
      value: 'about',
      to: '/about',
    },
  ];
</script>

<template>
  <v-navigation-drawer>
    <v-list nav density="comfortable">
      <template v-for="nav in navs" :key="nav.value">
        <v-list-item
          density="compact"
          :prepend-icon="nav.prependIcon"
          :title="nav.title"
          :value="nav.value"
          :to="nav.to"
        />
      </template>
    </v-list>
  </v-navigation-drawer>
</template>
