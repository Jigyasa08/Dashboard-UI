<template>
  <div class="dashboard">
    <div class="sidebar">
      <h1>CRM.io</h1>
      <nav>
        <ul>
          <li>Dashboard</li>
          <li>Document</li>
          <li>Contact</li>
          <li>Prospect</li>
          <li>Workflow</li>
          <li>Chat Integration</li>
          <li>Marketing Automation</li>
          <li>Email Integration</li>
          <li>Transaction</li>
          <li>Maintenance</li>
        </ul>
      </nav>
    </div>
    <div class="main-content">
      <header>
        <h2>Overview</h2>
      </header>
      <section class="stats">
        <div class="stat-box">
          <h3>Document</h3>
          <p>146,000</p>
          <span>Since last week</span>
        </div>
        <div class="stat-box">
          <h3>Contact</h3>
          <p>1,400</p>
          <span>Since last week</span>
        </div>
        <div class="stat-box">
          <h3>Email</h3>
          <p>150,700</p>
          <span>Since last week</span>
        </div>
      </section>
      <section class="charts">
        <LineChart />
        <BarChart />
      </section>
      <section class="documents">
        <h3>Document Tracking Information</h3>
        <table>
          <thead>
            <tr>
              <th>Name</th>
              <th>File</th>
              <th>Category</th>
              <th>Author</th>
              <th>Status</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Annual Report</td>
              <td>PDF</td>
              <td>Property</td>
              <td>Diana Matthews</td>
              <td>Send</td>
            </tr>
            <tr>
              <td>Business Plan</td>
              <td>WORD</td>
              <td>Cryptocurrency</td>
              <td>Philip James</td>
              <td>Send</td>
            </tr>
            <tr>
              <td>Marketing Tool</td>
              <td>PDF</td>
              <td>Content Creator</td>
              <td>Amanda Ross</td>
              <td>Pending</td>
            </tr>
          </tbody>
        </table>
      </section>
    </div>
    <div class="admin">
      <span class="user-info">Administrator</span>
      <div class="side-box"></div>
    </div>
  </div>
</template>

<script>
import LineChart from "./LineChart.vue";
import BarChart from "./BarChart.vue";

export default {
  name: "DashboardView",
  components: {
    LineChart,
    BarChart,
  },
};
</script>

<style scoped>
.dashboard {
  display: flex;
  /* min-height: 100vh; */
  background-color: #f1f1f1;
}

.sidebar {
  width: 250px;
  background-color: #001f3f;
  color: white;
  padding: 20px 50px;
  flex-grow: 0;
}

.sidebar h1 {
  color: #ff4136;
  text-align: left;
}

.sidebar nav ul {
  list-style-type: none;
  padding: 0;
  text-align: left;
}

.sidebar nav ul li {
  margin: 20px 0;
  cursor: pointer;
}

.main-content {
  width: 60%;
  padding: 20px;
  display: flex;
  flex-direction: column;
  padding: 20px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  min-width: 0;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.stats {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}

.stat-box {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
  flex: 1 1 1 30%;
  text-align: center;
  min-width: 200px;
}

.charts {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
  margin: 20px 0;
}

.charts canvas {
  flex: 1 1 45%;
  min-width: 300px;
  background-color: white;
  border-radius: 5px;
}

.documents {
  margin-top: 20px;
  background-color: white;
  border-radius: 5px;
}

table {
  width: 100%;
  border-collapse: collapse;
}

table,
th,
td {
  border: 1px solid #ddd;
}

th,
td {
  padding: 15px;
  text-align: left;
}

.admin {
  width: 15%;
  padding-top: 40px;
}

.user-info {
  /* background-color: #FF4136; */
  padding: 10px;
  cursor: pointer;
  /* border-radius: 5%;  */
  /* color: white; */
}

.side-box {
  background-color: white;
  margin-top: 50px;
  height: 70%;
  border-radius: 5px;
}
</style>
