<template>
  <v-app>
    <v-main>
      <code-editor />
    </v-main>
  </v-app>
</template>

<script>
import CodeEditor from "./components/CodEditor.vue";

export default {
  name: "App",

  components: {
    CodeEditor
  },

  data: () => ({
    //
  })
};
</script>
<style>
body {
  color: white;
  font: 1.3rem Inconsolata, monospace;
}
</style>
