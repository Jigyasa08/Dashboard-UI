`
<template>
  <div class="stat-box">
    <h3>{{ title }}</h3>
    <p>{{ value }}</p>
    <span class="trend">
      <font-awesome-icon :icon="icon" />
      {{ trend }}
    </span>
    <span class="subtitle">{{ subtitle }}</span>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

export default {
  name: "StatBox",
  components: {
    FontAwesomeIcon,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    value: {
      type: [String, Number],
      required: true,
    },
    icon: {
      type: Array,
      required: true,
    },
    trend: {
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
  padding: 0 20px 20px 20px;
  border-radius: 5px;
  flex-grow: 1;
  min-width: 200px;
}

.stat-box h3 {
  margin-bottom: 40px;
}

.stat-box p {
  font-weight: bold;
  font-size: 1.7em;
  margin-bottom: 0px;
}

.trend {
  font-size: 0.8em;
  color: green;
  margin-right: 10px;
}

.subtitle {
  font-size: 0.8em;
}
</style>
`
