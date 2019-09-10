<template>
  <div id="app">
    <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
  </div>
</template>

<script>
// ⚠️ NOTE: We don't use @ckeditor/ckeditor5-build-classic any more!
// Since we're building CKEditor from source, we use the source version of ClassicEditor.
import ClassicEditor from "@ckeditor/ckeditor5-editor-classic/src/classiceditor";
import EssentialsPlugin from "@ckeditor/ckeditor5-essentials/src/essentials";
import BoldPlugin from "@ckeditor/ckeditor5-basic-styles/src/bold";
import ItalicPlugin from "@ckeditor/ckeditor5-basic-styles/src/italic";
import LinkPlugin from "@ckeditor/ckeditor5-link/src/link";
import ParagraphPlugin from "@ckeditor/ckeditor5-paragraph/src/paragraph";
// import Alignment from "@ckeditor/ckeditor5-alignment/src/alignment";
//import RemoveFormat from '@ckeditor/ckeditor5-remove-format/src/removeformat';
//import WordCount from "@ckeditor/ckeditor5-word-count/src/wordcount";
// import Highlight from '@ckeditor/ckeditor5-highlight/src/highlight';
//import WordCount from '@ckeditor/ckeditor5-word-count/src/wordcount';
export default {
  name: "app",
  data() {
    return {
      editor: ClassicEditor,
      editorData: "<p>Content of the editor.</p>",
      editorConfig: {
        plugins: [
          EssentialsPlugin,
          BoldPlugin,
          ItalicPlugin,
          LinkPlugin,
          ParagraphPlugin,
        //   Alignment
          //   WordCount
          //   Highlight
          //RemoveFormat
          // wordCount
        ],

        toolbar: {
          items: ["bold", "italic", "link", "undo", "redo", "alignment"]
        }
      }
    };
  }
};
</script>