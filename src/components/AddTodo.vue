<template>
  <div>
    <h3>Add Todo</h3>
    <div class="add">
      <form @submit="onSumbit">
        <input type="text" v-model="title" placeholder="Add Todo...">
        <input type="submit" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';

export default {
  name:'AddTodo',
  data() {
    return {
      // connecting it to the v-model
      title: ''
    }
  },
  methods: {
    ...mapActions(['addTodo']),
    onSumbit(e){
      e.preventDefault();
      //we got the addTodo method from the action, it takes in a title arguement
      this.addTodo(this.title);
      //clear the form
      this.title = '';
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #41b883;
  outline: 0;
}
input[type="submit"] {
  flex: 2;
  background: #41b883;
  color: #fff;
  border: 1px #41b883 solid;
  cursor: pointer;
}
</style>

