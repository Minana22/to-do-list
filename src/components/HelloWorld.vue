<template>
  <div class="main">
    <div class="toDo">
      <button @click="addTask(n)" class="btn" v-for="n in toDoniz" :key="n">
        {{ n }}
      </button>
    </div>
    <div class="push">
      <button @click="removeTask(n)" class="btn" v-for="n in doneNiz" :key="n">
        {{ n }}
      </button>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      toDoniz: ["task 1", "task 2", "task 3", "task 4", "task 5", "task 6"],
      doneNiz: [],
    };
  },
  name: "HelloWorld",
  methods: {
    addTask(task) {
      this.toDoniz = this.toDoniz.filter((t) => t !== task);
      this.doneNiz.push(task);
    },
    removeTask(task) {
      this.doneNiz = this.doneNiz.filter((t) => t !== task);
      this.toDoniz.push(task);
    },
  },
};
</script>

<style scoped>
.main {
  width: 100%;
  height: 90vh;
  background-color: rgb(21, 128, 124);
  display: flex;
  justify-content: center;
}
.btn {
  width: 200px;
  height: 80px;
  margin: 10px;
  background-color: rgb(154, 223, 218);
  cursor: pointer;
}
.toDo {
  border: 5px solid rgb(5, 83, 48);
  width: 20%;
  background-color: rgb(214, 172, 253);
  display: flex;
  flex-direction: column;
  margin: 10px;
  align-items: center;
}
.push {
  border: 5px solid rgb(5, 83, 48);
  width: 20%;
  background-color: rgb(201, 154, 244);
  display: flex;
  flex-direction: column;
  margin: 10px;
  align-items: center;
}
</style>
