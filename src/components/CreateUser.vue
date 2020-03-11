<template>
  <div class="form">
    <form @submit.prevent="addUser">
      <div class="input-field">
        <input type="text" v-model="title" placeholder="Enter Post" />
      </div>
      <button class="btn red">Add user</button>
    </form>
  </div>
</template>

<script>
import uuid from 'uuid/v1';
import axios from 'axios';

export default {
  name: 'CreateUser',
  data() {
    return {
      id: uuid,
      title: ''
    };
  },
  methods: {
    addUser() {
      const user = {
        id: this.id,
        title: this.title
      };
      axios
        .post('https://jsonplaceholder.typicode.com/todos', user)
        .then(res => console.log(res.data))
        .catch(err => console.log(err));
      this.title = '';
    }
  }
};
</script>

<style></style>
