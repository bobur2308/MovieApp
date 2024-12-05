<template>
  <div>
    <h1>{{ message }}</h1>
    <button @click="updateMessage">Click Me</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 0,
    };
  },
  methods: {
    updateMessage() {
      this.message += 1 ;
    },
  },
};
</script>
