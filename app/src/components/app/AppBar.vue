<script setup lang="ts">
  // props
  interface Props {
    title: string;
    isDarkTheme: boolean;
  }
  withDefaults(defineProps<Props>(), {
    title: 'title',
    isDarkTheme: false,
  });

  // emits
  interface Emits {
    (e: 'clickBarNavIcon'): void;
    (e: 'clickThemeIcon'): void;
  }
  const emits = defineEmits<Emits>();
  const onClickBarNavIcon = (): void => {
    emits('clickBarNavIcon');
  };
  const onClickThemeIcon = (): void => {
    emits('clickThemeIcon');
  };
</script>

<template>
  <v-app-bar density="compact" elevation="1">
    <template #prepend>
      <v-app-bar-nav-icon @click="onClickBarNavIcon()" />
    </template>

    <v-app-bar-title>{{ title }}</v-app-bar-title>

    <template #append>
      <v-btn icon @click="onClickThemeIcon()">
        <v-icon v-if="isDarkTheme">mdi-weather-night</v-icon>
        <v-icon v-else>mdi-weather-sunny</v-icon>
      </v-btn>
    </template>
  </v-app-bar>
</template>
