<template>
<div>
  <div style="display:flex;">
    <editor
      v-model="content"
      @init="editorInit"
      lang="python"
      theme="twilight"
      width="1200"
      height="500"
    >    
    </editor>
    <div>
      <v-btn @click="send_code()" class="my-2 mx-2" fab dark small color="primary">
      <v-icon dark>
        mdi-play
      </v-icon>
    </v-btn>
    </div>
  </div>
      <div style="height:270px;background-color: lightgrey; font: 1.0rem Inconsolata, monospace;">{{ res }}</div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      content: null,
      res: null
    };
  },
  components: {
    editor: require("vue2-ace-editor")
  },
  methods: {
    editorInit: function() {
      require("brace/ext/language_tools"); //language extension prerequsite...
      require("brace/mode/html");
      require("brace/mode/python"); //language
      require("brace/mode/less");
      require("brace/theme/twilight");
      require("brace/snippets/javascript"); //snippet
    },
    send_code: function() {
      axios
        .post("http://127.0.0.1:8000/getfile", { data: String(this.content) })
        .then(response => {
          console.log(this.content);
          this.res = response.data;
          console.log(response);
        });
    }
  }
};
</script>

<style></style>
