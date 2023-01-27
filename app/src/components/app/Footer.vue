<script setup lang="ts">
  // props
  interface Props {
    ownerName: string;
    publishedYear: number;
  }
  defineProps<Props>();

  const nowYear = new Date().getFullYear();
</script>

<template>
  <v-footer app order="-1" elevation="2">
    <v-row justify="center" no-gutters>
      <v-col class="text-center" cols="12">
        <span>© </span>
        <span v-if="publishedYear < nowYear"> {{ publishedYear }} — </span>
        <span class="mr-2">{{ nowYear }}</span>
        <span>
          <strong>{{ ownerName }}</strong>
        </span>
      </v-col>
    </v-row>
  </v-footer>
</template>
