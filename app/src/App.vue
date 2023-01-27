<script setup lang="ts">
  import { ref } from 'vue';

  import AppBar from '@/components/app/AppBar.vue';
  import NavigationDrawer from '@/components/app/NavigationDrawer.vue';
  import MainView from '@/components/app/MainView.vue';
  import Footer from '@/components/app/Footer.vue';

  // params
  const title: string = 'Example title';
  const ownerName: string = 'Example owner mame';
  const publishedYear: number = 2023;

  // refs
  const drawer = ref(false);
  const THEMES = {
    Light: 'light',
    Dark: 'dark',
  };
  const theme = ref(THEMES.Light);

  // functions
  const switchTheme = () => {
    theme.value = theme.value === THEMES.Light ? THEMES.Dark : THEMES.Light;
  };
</script>

<template>
  <v-app :theme="theme">
    <AppBar
      :title="title"
      color="primary"
      @click-bar-nav-icon="drawer = !drawer"
      @click-theme-icon="switchTheme"
    />
    <NavigationDrawer v-model="drawer" />
    <MainView />
    <Footer
      :owner-name="ownerName"
      :published-year="publishedYear"
      color="primary"
    />
  </v-app>
</template>
