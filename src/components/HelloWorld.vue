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
  v-for="item in props.items"
  :key="item.id"
  >

    <span v-text="item.name"></span>
    <span v-text="item.age"></span>

  </div>

  <button 
  @click="display('name')"
  >
    Display Name
  </button>

  <button
   @click="display('age')"
   >
    Display Age
  </button>
</template>

<script setup lang="ts">

  import type { UserTypes } from 'types/User';
  import type { UserProperty} from 'types/UserProperty';
  import { reactive, ref } from 'vue';
  
  const props = defineProps<{
    items: UserTypes[],
  }>();

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

  
  const display = (property: UserProperty) => {
    props.items.forEach((item: UserTypes) => {
      console.log(item[property]);
    });
  }

</script>
