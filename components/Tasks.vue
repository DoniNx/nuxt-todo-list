<template>
  <div class="mother">
    <details v-for="task in Tasks" :key="task.id">
      <summary>{{ task.author }}</summary>
      {{ task.text }}
    </details>
  </div>
</template>



<script>
export default {
  data() {
    return {};
  },
  name: "Tasks",
  props: {
    Tasks: Array,
  },
};
</script>


<style scoped>
* {
  margin: 0;
  box-sizing: border-box;
  padding: 0;
}
.mother {
  padding: 1em 2em;
  border: solid rgb(65, 3, 3) 3px;
  margin: 1em 0;
}
summary {
  text-transform: uppercase;
}
details {
  font-family: sans-serif;
  margin: 4px 0;
}
</style>