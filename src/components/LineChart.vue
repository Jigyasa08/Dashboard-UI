<template>
  <canvas ref="lineChart"></canvas>
</template>

<script>
import { onMounted, ref } from "vue";
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
  setup() {
    const lineChart = ref(null);

    onMounted(() => {
      const ctx = lineChart.value.getContext("2d");
      new Chart(ctx, {
        type: "line",
        data: {
          labels: [
            "Jan",
            "Feb",
            "Mar",
            "Apr",
            "May",
            "Jun",
            "Jul",
            "Aug",
            "Sep",
            "Oct",
            "Nov",
            "Dec",
          ],
          datasets: [
            {
              label: "Recent Workflow",
              data: [12, 19, 3, 5, 2, 3, 10, 15, 20, 25, 30, 35],
              borderColor: "rgba(75, 192, 192, 1)",
              borderWidth: 1,
              fill: false,
            },
          ],
        },
        options: {
          responsive: true,
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
  min-width: 300px;
  height: 200px;
  background-color: white;
  border-radius: 5px;
}
</style>
