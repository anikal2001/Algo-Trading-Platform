<template>
  <codemirror ref="myCm" :options="cmOptions"> </codemirror>
</template>

<script>
// language js
import "codemirror/mode/python/python.js";
// theme css
import "codemirror/theme/base16-dark.css";
// more codemirror resources
// import 'codemirror/some-resource...'
import { codemirror } from "vue-codemirror";

// require styles
import "codemirror/lib/codemirror.css";
export default {
  components: {
    codemirror
  },
  data() {
    return {
      cmOptions: {
        // codemirror options
        tabSize: 4,
        mode: "text/python",
        theme: "base16-dark",
        lineNumbers: true,
        line: true
      }
    };
  }
};
</script>

<style></style>
