<template>
  <div class="dashboard">
    <NavBar />
    <div class="main-content">
      <header>
        <h2>Overview</h2>
      </header>
      <section class="stats">
        <StatBox title="Document" value="146,000" subtitle="Since last week" />
        <StatBox title="Contact" value="1,400" subtitle="Since last week" />
        <StatBox title="Email" value="150,700" subtitle="Since last week" />
      </section>
      <section class="charts">
        <LineChart />
        <BarChart />
      </section>
      <TableData :documents="documents" />
    </div>
    <div class="admin">
      <div>
        <span class="user-info">Administrator</span>
        <FontAwesomeIcon :icon="faChevronDown" />
      </div>
      <div class="side-box"></div>
    </div>
  </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import StatBox from "./StatBox.vue";
import LineChart from "./LineChart.vue";
import BarChart from "./BarChart.vue";
import TableData from "./TableData.vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faChevronDown } from "@fortawesome/free-solid-svg-icons";

export default {
  name: "DashboardView",
  components: {
    NavBar,
    StatBox,
    LineChart,
    BarChart,
    TableData,
    FontAwesomeIcon,
  },
  data() {
    return {
      faChevronDown,
      documents: [
        {
          name: "Annual Report",
          file: "PDF",
          category: "Property",
          author: "Diana Matthews",
          status: "Send",
        },
        {
          name: "Business Plan",
          file: "WORD",
          category: "Cryptocurrency",
          author: "Philip James",
          status: "Send",
        },
        {
          name: "Marketing Tool",
          file: "PDF",
          category: "Content Creator",
          author: "Amanda Ross",
          status: "Pending",
        },
      ],
    };
  },
};
</script>

<style scoped>
.dashboard {
  display: flex;
  height: 100vh;
  background-color: #f1f1f1;
  overflow-y: hidden;
}

/* .sidebar {
  width: 250px;
  background-color: #001f3f;
  color: white;
  flex-grow: 0;
  flex-shrink: 0;
} */

/* .sidebar h1 {
  padding: 20px 50px;
} */

/* nav {
  padding: 0 50px;
} */

/* .sidebar h1 {
  color: #ff4136;
  text-align: left;
} */

/* .sidebar nav ul {
  list-style-type: none;
  padding: 0;
  text-align: left;
} */

/* .sidebar nav ul li {
  margin: 20px 0;
  cursor: pointer;
} */

.main-content {
  width: 60%;
  padding-inline: 20px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  min-width: 0;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  /* margin-bottom: 20px; */
}

.stats {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}

/* .stat-box {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
  flex: 1 1 30%;
  text-align: center;
  min-width: 200px;
  flex-grow: 1;
  flex-basis: 0;
} */

.charts {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
  margin: 20px 0;
  height: 200px;
}

.charts canvas {
  flex: 1 1 45%;
  min-width: 300px;
  background-color: white;
  border-radius: 5px;
}

.admin {
  width: 15%;
  padding-top: 20px;
}

.user-info {
  padding: 10px;
  cursor: pointer;
}

.side-box {
  background-color: white;
  margin-top: 30px;
  height: 70%;
  border-radius: 5px;
}
</style>
