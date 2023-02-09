<script setup lang="ts">
import { RouterView } from "vue-router";
// Using ES modules (default)
import PocketBase from "pocketbase";
const pb = new PocketBase("http://127.0.0.1:8090/");

// you can also fetch all records at once via getFullList
const resultList = await pb.collection('endpoint').getList(1, 50, {
  expand: 'api',
});

console.log(resultList)
</script>

<template>
  <RouterView />
</template>
