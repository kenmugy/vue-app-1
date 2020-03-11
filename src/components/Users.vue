<template>
  <div class="users">
    <div
      class="card-panel container black"
      v-for="user in users"
      :key="user.id"
    >
      <h1 class="white-text">{{ user.title }}</h1>
      <h3 class="red-text">{{ user.id }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Users',
  props: ['users']
};
</script>

<style></style>
