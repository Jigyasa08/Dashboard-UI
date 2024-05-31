<template>
  <canvas height="200" ref="barChart"></canvas>
</template>

<script>
import { onMounted, ref, toRefs } from "vue";
import {
  Chart,
  BarController,
  BarElement,
  LinearScale,
  Title,
  CategoryScale,
} from "chart.js";

Chart.register(BarController, BarElement, LinearScale, Title, CategoryScale);

export default {
  name: "BarChart",
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
      default: () => ({
        backgroundColor: "rgba(153, 102, 255, 0.6)",
        borderColor: "rgba(153, 102, 255, 1)",
        borderWidth: 1,
      }),
    },
  },
  setup(props) {
    const { labels, data, title, options } = toRefs(props);
    const barChart = ref(null);

    onMounted(() => {
      const ctx = barChart.value.getContext("2d");
      new Chart(ctx, {
        type: "bar",
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
      barChart,
    };
  },
};
</script>

<style>
canvas {
  flex: 1 1 45%;
  width: 300px;
  height: 200px;
  background-color: white;
  border-radius: 5px;
}
</style>
