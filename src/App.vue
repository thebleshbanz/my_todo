<template>
  <div class="container">
    <Header title="My ToDo Tasks" />
    <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
  
import Header from "./components/Header";
import Tasks from "./components/Tasks";

export default {
  name: "App",
  components: {
    Header,
    Tasks
  },
  data() {
    return {
      tasks: []
    };
  },
  methods: {
    deleteTask(id) {
      // console.log('task', id)
      if (confirm("Are you Sure?")) {
        this.tasks = this.tasks.filter(task => task.id !== id);
      }
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Clinet Meeting On Zoom",
        day: "May 24th at 1:30 PM",
        reminder: true
      },
      {
        id: 2,
        text: "Lunch with CEO sir",
        day: "May 23th at 12:30 PM",
        reminder: true
      },
      {
        id: 3,
        text: "Watch Cricket Match of Ind vs Aust ",
        day: "May 23th at 1:30 PM",
        reminder: false
      }
    ];
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
