<template>
  <div class="inputbox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" />
    <!-- <button v-on:click="addTodo">add</button> -->
    <span class="addContainer" v-on:click="addTodo">
      <!-- <i class="fa-solid fa-plus addBtn"></i> -->
      <!-- <font-awesome-icon icon="fa-solid fa-user-secret addBtn" /> -->
      <i class="fa-solid fa-plus addBtn"></i>
    </span>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    addTodo: function () {
      if (this.newTodoItem !== "") {
        this.$emit('addTodoItem', this.newTodoItem);
        this.clearInput();
      }
    },
    clearInput: function () {
      this.newTodoItem = "";
    },
  },
};
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputbox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputbox input {
  /* border-style: none;
  font-size: 0.9rem; */
  height: 40px;

  width: 80%;

  border-style: none;

  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, blue, purple);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;

  width: 50px;

  vertical-align: middle;
}
</style>