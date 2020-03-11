<template>
  <div class="app">
    <Counter />
    <CreateUser addUser() />
    <Users :users="users" />
  </div>
</template>

<script>
import Counter from './components/Counter';
import Users from './components/Users';
import CreateUser from './components/CreateUser';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Counter,
    Users,
    CreateUser
  },
  data() {
    return {
      users: []
    };
  },
  created() {
    axios
      .get('https://jsonplaceholder.typicode.com/todos')
      .then(res => (this.users = res.data))
      .catch(err => console.log(err));
  }
};
</script>

<style scoped>
.app {
  width: 80%;
  margin: 0 auto;
}
</style>
