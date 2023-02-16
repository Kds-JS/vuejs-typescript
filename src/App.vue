<template>
  <HelloWorld  :items="items"/>
</template>

<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue';
import type {UserTypes} from 'types/User';
import { ref } from 'vue';

const items = ref<UserTypes[]>([
    {
      id: 1,
      name: 'Nord',
      age: 18
    },
    {
      id: 2,
      name: 'Kds',
      age: 45
    }
  ]);
</script>


