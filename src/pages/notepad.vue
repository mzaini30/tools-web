<script setup="" lang="ts">
import { Head } from "@vueuse/head";
import { ref, watch } from "vue";

const isinya = ref("");

if (localStorage.notepad) {
  isinya.value = localStorage.notepad;
}

watch(
  () => isinya.value,
  () => (localStorage.notepad = isinya.value)
);
</script>

<template>
  <Head>
    <title>Notepad</title>
  </Head>
  <div class="w-full p-5 bg-green-500 h-screen">
    <textarea
      class="focus:outline-none border border-black w-full p-5 bg-gray-200"
      name=""
      id=""
      cols="30"
      rows="10"
      v-model="isinya"
    ></textarea>
  </div>
</template>

<style scoped="">
textarea {
  box-shadow: 10px 10px 0 0 black;
  height: calc(100vh - 3rem);
}
</style>
