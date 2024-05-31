<template>
  <div class="dashboard">
    <NavBar />
    <div class="main-content">
      <header>
        <h2>Overview</h2>
        <font-awesome-icon class="bell-icon fa-regular" :icon="bellIcon" />
      </header>
      <section class="stats">
        <StatBox
          v-for="stat in stats"
          :key="stat.id"
          :title="stat.title"
          :value="stat.value"
          :trend="stat.trend"
          :subtitle="stat.subtitle"
        />
      </section>
      <section class="charts">
        <LineChart
          :labels="lineChartLabels"
          :data="lineChartData"
          title="Recent Workflow"
        />
        <BarChart
          :labels="barChartLabels"
          :data="barChartData"
          title="Recent Marketing"
        />
      </section>
      <TableData :documents="documents" />
    </div>
    <div class="admin">
      <div class="user-info">
        <ProfileAvatar name="Administrator" fontWeight="" />
        <FontAwesomeIcon class="icon" :icon="faChevronDown" />
      </div>
      <RightSidebar />
    </div>
  </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import StatBox from "./StatBox.vue";
import LineChart from "./LineChart.vue";
import BarChart from "./BarChart.vue";
import TableData from "./TableData.vue";
import ProfileAvatar from "./ProfileAvatar.vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faChevronDown } from "@fortawesome/free-solid-svg-icons";
import { faBell } from "@fortawesome/free-solid-svg-icons";
import RightSidebar from "./RightSidebar.vue";

export default {
  name: "DashboardView",
  components: {
    NavBar,
    StatBox,
    LineChart,
    BarChart,
    TableData,
    FontAwesomeIcon,
    ProfileAvatar,
    RightSidebar,
  },
  data() {
    return {
      faChevronDown,
      bellIcon: faBell,
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
      lineChartLabels: [
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
      lineChartData: [12, 19, 3, 5, 2, 3, 10, 15, 20, 25, 30, 35],
      barChartLabels: [
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
      barChartData: [5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60],
      stats: [
        {
          id: "1",
          title: "Document",
          value: "146,000",
          trend: "17%",
          subtitle: "Since last week",
        },
        {
          id: "2",
          title: "Contact",
          value: "1,400",
          trend: "17%",
          subtitle: "Since last week",
        },
        {
          id: "3",
          title: "Email",
          value: "150,700",
          trend: "17%",
          subtitle: "Since last week",
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
}

.stats {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

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
  padding-top: 15px;
}

.user-info {
  display: flex;
  cursor: pointer;
}

.icon {
  margin: 15px;
  font-size: 0.7em;
}

.bell-icon {
  fill: none;
  font-size: 1.2rem;
  margin-right: 10px;
}
</style>
