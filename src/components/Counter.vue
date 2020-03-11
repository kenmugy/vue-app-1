<template>
  <div class="couter">
    <p>counter</p>
    <h1>{{ count }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  data() {
    return {
      count: 0
    };
  }
};
</script>

<style></style>
