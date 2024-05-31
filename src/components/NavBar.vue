<!-- NavBar.vue -->
<template>
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
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.sidebar {
  width: 250px;
  background-color: #001f3f;
  color: white;
  flex-shrink: 0;
}

.sidebar h1 {
  padding: 20px 50px;
}

nav {
  padding: 0 50px;
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
</style>
