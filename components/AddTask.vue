<template>
  <div class="container">
    Author:
    <input type="text" v-model="author" placeholder="Author" />
    <br />
    TODO:
    <input type="text" v-model="text" placeholder="TODO item" />
    <button @click="onSubmit">Add Task</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      author: "",
      text: "",
    };
  },
  methods: {
    onSubmit: function (e) {
      e.preventDefault();
      if (this.author == "" || this.text == "") {
        alert("Enter something");
        return;
      }
      let newTask = {
        id: Math.floor(Math.random() * 100000),
        author: this.author,
        text: this.text,
      };
      this.author = "";
      this.text = "";
      this.$emit("add-task", newTask);
    },
  },
};
</script>

<style scope>
* {
  font-family: sans-serif;
}
.container {
  border: solid 4px rgb(83, 1, 1);
  padding: 1em 2em;
  display: flex;
  flex-direction: column;
  align-items: center;
}
button {
  margin: 1em 0;
  background: greenyellow;
  padding: 4px 7px;
  border: none;
}
</style>