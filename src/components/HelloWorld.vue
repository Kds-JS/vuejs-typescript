<template>
  <h1
  v-text="title" 
  > 
   
  </h1>

  <h2
  v-text="subTitle" 
  > 
   
  </h2>

  <button
  @click="editTitle('Hello World Edited')"
  >
    Editer title
  </button>

  <button
  @click="editSubTitle('80')"
  >
    Editer subTitle
  </button>


  <div
  v-for="item in items"
  :key="item.id"
  >

    <span v-text="item.name"></span>
    <span v-text="item.age"></span>

  </div>
</template>

<script setup lang="ts">

  import { reactive, ref } from 'vue';
  import type {UserTypes} from '../../types/User'

  // const title: string = 'Hello World';
  // const subtitle: number | string  = 90;

  // const state = reactive ( {
  //   title: 'Hello World' as string,
  //   subTitle: 90 as string | number,
  // });

  const title = ref<string>('Hello World');
  const subTitle = ref<string | number>(90);

  // console.log(title.value);

  const editTitle = (editTitle : string) => {
    title.value = editTitle;
  }

  const editSubTitle = (editSubTitle : string | number) => {
    subTitle.value = editSubTitle;
  }

  const items = ref<UserTypes[]>([
    {
      id: 1,
      name: 'Nord',
      age: 18
    },
    {
      id: 2,
      name: 'Kds',
      age: 35
    }
  ]);


</script>
