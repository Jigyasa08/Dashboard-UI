<template>
  <div class="stat-box">
    <h3>{{ title }}</h3>
    <p>{{ value }}</p>
    <span>{{ subtitle }}</span>
  </div>
</template>

<script>
export default {
  name: "StatBox",
  props: {
    title: {
      type: String,
      required: true,
    },
    value: {
      type: [String, Number],
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.stat-box {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
  text-align: center;
  flex-grow: 1;
  min-width: 200px;
}
</style>
