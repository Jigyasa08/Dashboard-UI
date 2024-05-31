<template>
  <canvas height="200" ref="lineChart"></canvas>
</template>

<script>
import { onMounted, ref, toRefs } from "vue";
import {
  Chart,
  LineController,
  LineElement,
  PointElement,
  LinearScale,
  Title,
  CategoryScale,
} from "chart.js";

Chart.register(
  LineController,
  LineElement,
  PointElement,
  LinearScale,
  Title,
  CategoryScale
);

export default {
  name: "LineChart",
  props: {
    labels: {
      type: Array,
      required: true,
    },
    data: {
      type: Array,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    options: {
      type: Object,
      required: false,
      default: function () {
        return {
          borderColor: "rgba(75, 192, 192, 1)",
          borderWidth: 1,
          fill: false,
        };
      },
    },
  },
  setup(props) {
    const { labels, data, title, options } = toRefs(props);
    const lineChart = ref(null);

    onMounted(() => {
      const ctx = lineChart.value.getContext("2d");
      new Chart(ctx, {
        type: "line",
        data: {
          labels: labels.value,
          datasets: [
            {
              label: title.value,
              data: data.value,
              ...options.value,
            },
          ],
        },
        options: {
          responsive: false,
        },
      });
    });

    return {
      lineChart,
    };
  },
};
</script>

<style scoped>
canvas {
  flex: 1 1 45%;
  width: 300px;
  height: 200px;
  background-color: white;
  border-radius: 5px;
}
</style>
