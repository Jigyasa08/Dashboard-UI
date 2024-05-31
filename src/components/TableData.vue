<!-- DataTable.vue -->
<template>
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
        <tr v-for="document in documents" :key="document.name">
          <td>{{ document.name }}</td>
          <td>{{ document.file }}</td>
          <td>{{ document.category }}</td>
          <td>{{ document.author }}</td>
          <td>{{ document.status }}</td>
        </tr>
      </tbody>
    </table>
  </section>
</template>

<script>
export default {
  name: "DataTable",
  props: {
    documents: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.documents {
  background-color: white;
  border-radius: 5px;
  /* overflow-y: auto; */
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
</style>
