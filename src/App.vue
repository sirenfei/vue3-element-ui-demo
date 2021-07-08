<template>
  <el-container>
    <el-header
      >If Element Plus is successfully added to this project, you'll see
      an</el-header
    >

    <el-main>

      <el-space wrap size="large">
        <el-card class="box-card" style="width: 250px" v-for="i in 3" :key="i">
          <template #header>
            <div class="card-header">
              <span>Card name</span>
              <el-button class="button" type="text">Operation button</el-button>
            </div>
          </template>
          <div><img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png" class="image"></div>
        </el-card>
      </el-space>

      <el-space wrap size="large">
        <el-card class="box-card" style="width: 250px" v-for="i in 3" :key="i">
          <template #header>
            <div class="card-header">
              <span>Card name</span>
              <el-button class="button" type="text">Operation button</el-button>
            </div>
          </template>
          <div v-for="o in 4" :key="o" class="text item">
            {{ "List item " + o }}
          </div>
        </el-card>
      </el-space>
    </el-main>
  </el-container>
</template>

<script>
import { computed, ref, watch, reactive } from "@vue/runtime-core";

export default {
  name: "App",
  components: {},
  setup() {
    let todos = ref([]);
    let todoCount = computed(() => {
      return todos.value.length;
    });

    let data = reactive({
      todos: [],
    });

    function addTodo() {
      console.log("1111111");
    }

    watch(todos, (newTodo) => {
      console.log(newTodo);
    });
    return {
      todoCount,
      data,
      addTodo,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
