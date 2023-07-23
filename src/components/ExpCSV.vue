<template>
<head>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css">
</head>
  <div class="container">
    <div id="app">
      <div> 
        <p class="btn btn-primary float-end" @click="exportToCSV">
          <i class="pl-4 bi bi-download"></i> Export to CSV
        </p>
      </div>

      <table class="table table-striped table-bordered">
        <thead>
          <tr>
            <th>Asset name</th>
            <th>Department</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(asset, index) in assets" :key="index">
            <td>{{ asset.name }}</td>
            <td>{{ asset.department }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      assets: [
        { name: 'Printer', department: 'HR' },
        { name: 'Monitor', department: 'IT' },
        { name: 'Barcode Scanner', department: 'ACCOUNT' },
      ],
    };
  },
  methods: {
    exportToCSV() {
      // Create the header row
      const headerRow = 'Asset name,Department';

      // Convert the assets data to CSV format
      const csvContent =
        'data:text/csv;charset=utf-8,' +
        headerRow +
        '\n' +
        this.assets.map((asset) => `${asset.name},${asset.department}`).join('\n');

      // Create a temporary anchor element to trigger the download
      const encodedUri = encodeURI(csvContent);
      const link = document.createElement('a');
      link.setAttribute('href', encodedUri);
      link.setAttribute('download', 'assets.csv');

      // Append the anchor element to the DOM and click it to start the download
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    },
  },
  props: {
    msg: String,
  },
};
</script>
 