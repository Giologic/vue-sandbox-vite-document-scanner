<script setup lang="ts">
import useFileUpload from './composables/use-file-upload';
import dummy from './assets/dummy.json';

type OCRDocument = {
  page: string;
  blocks: Array<string>;
};

const dummyFile = new File(['foo'], 'foo.txt', {
  type: 'text/plain',
});

const { data, error, isLoading, uploadFile } = useFileUpload<OCRDocument>({
  url: dummy,
});
</script>

<template>
  <div>File Upload</div>
  <button @click="() => uploadFile(dummyFile)">Button</button>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
