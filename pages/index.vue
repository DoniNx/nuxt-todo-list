<template>
  <div>
    <Tutorial />
    <AddTask @add-task="addTask" />
    <Tasks :Tasks="Tasks" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      Tasks: [],
      showTasks: false,
    };
  },
  methods: {
    addTask: function (newTask) {
      this.Tasks.push(newTask);
    },
  },
  created() {
    this.Tasks = [
      {
        id: 233,
        author: "john",
        text: "kill the cat",
      },
      {
        id: 346,
        author: "john",
        text: "kill the cat",
      },
    ];
  },
};
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
  padding: 0;
}
</style>