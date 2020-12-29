<template>
  <section>
    <div class="container-fluid">
      <div class="row text-light">
        <div class="col-md-6">
          <h3>Editor</h3>
        </div>
        <div class="col-md-6">
          <h3>Previewer</h3>
        </div>
      </div>
    </div>
    <editor
      v-model="content"
      ref="”aceeditor”"
      @init="editorInit"
      lang="”markdown”"
      theme="dracula"
      :height="height"
    ></editor>
  </section>
</template>

<script>
export default {
  name: "HelloWorld",
  components: {
    editor: require("vue2-ace-editor")
  },
  props: {
    msg: String,
  },
  data() {
    return {
      content: "",
      height: window.innerHeight - 100
    };
  },
  methods: {
    editorInit() {
      require("brace/ext/language_tools");
      require("brace/mode/markdown");
      require("brace/theme/dracula");
    }
  }
};
</script>
