<template>
  <div class="hello">
    <h1>{{msg}}</h1>
      <vue-editor v-model="msg" :editorToolbar="customToolbar">></vue-editor>
<br><br><br>

      <vue-editor v-model="msg" :editorOptions="editorSettings">></vue-editor>
      
  </div>
</template>

<script>
import { VueEditor, Quill } from "vue2-editor";
import * as Emoji from "quill-emoji";
Quill.register("modules/emoji", Emoji);

import "quill-emoji/dist/quill-emoji.css";

//  import { ImageDrop } from 'quill-image-drop-module'
//   import ImageResize from 'quill-image-resize-module'
 
//   Quill.register('modules/imageDrop', ImageDrop)
//   Quill.register('modules/imageResize', ImageResize)
export default {
  name: 'MyTesting',
  components:{VueEditor,},
  data () {
    return {
      msg: 'Hello My Testing App !',
            customToolbar: [["bold", "italic", "underline"],['emoji'] ,[{ 'list': "ordered" }, { 'list': "bullet" }], ["image", "code-block"]],
editorSettings:{
  defaultValue:"",
  theme:"snow",
  modules:{
    toolbar : [['emoji']],
    "emoji-toolbar": true,
    // "emoji-textarea": true,
    "emoji-shortname": true,
  },

}

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
