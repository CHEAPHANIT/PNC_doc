<script setup lang="ts">
import HeaderMenu from '../../../src/Components/HeaderMenu.vue';
import NavbarAdmin from '../../Components/NavbarAdmin.vue';
import { ref } from 'vue';

const sidebarMenuItems = ref([
  { name: 'Dashboard', icon: 'home', route: '/admin/dashboard' },
  { name: 'Users', icon: 'user', route: '/admin/users' },
  { name: 'Orders', icon: 'shopping-cart', route: '/admin/orders' },
  { name: 'Products', icon: 'box', route: '/admin/products' },
  { name: 'Categories', icon: 'tags', route: '/admin/categories' },
  { name: 'Reports', icon: 'chart-bar', route: '/admin/reports' },
  { name: 'Settings', icon: 'cog', route: '/admin/settings' },
]);

</script>

<template>
  <div class="container-fluid">
    <NavbarAdmin />

    <div class="row flex-nowrap" style="margin-top: 7%;">
      <header-menu />

      <div class="d-flex flex-column bg-light rounded-lg" style="width: 86.8%; padding: 20px;">
        <div class="text-center mb-5">
          <h1 class="text-4xl md:text-6xl font-bold mb-4">Welcome to Dashboard</h1>
          <p class="text-lg md:text-2xl mb-8">Your journey to excellence starts here.</p>
          <p>Join Us Today and Get Started</p>
        </div>

        <div class="d-flex flex-wrap justify-content-around mb-5">
          <div v-for="item in sidebarMenuItems" :key="item.name" class="card m-3" style="width: 18rem;">
            <div class="card-body text-center">
              <i :class="`fas fa-${item.icon} fa-3x mb-3`"></i>
              <h5 class="card-title">{{ item.name }}</h5>
              <p class="card-text">Manage and view {{ item.name.toLowerCase() }}.</p>
              <a :href="item.route" class="btn btn-primary">Go to {{ item.name }}</a>
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6 mb-4">
            <div class="card">
              <div class="card-header">Recent Activities</div>
              <ul class="list-group list-group-flush">
                <li class="list-group-item">User John Doe created an order.</li>
                <li class="list-group-item">Product "XYZ" was added.</li>
                <li class="list-group-item">User Jane Smith updated her profile.</li>
              </ul>
            </div>
          </div>
          <div class="col-md-6 mb-4">
            <div class="card">
              <div class="card-header">Notifications</div>
              <ul class="list-group list-group-flush">
                <li class="list-group-item">New order received.</li>
                <li class="list-group-item">Product "ABC" is out of stock.</li>
                <li class="list-group-item">Server maintenance scheduled.</li>
              </ul>
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-12 mb-4">
            <div class="card">
              <div class="card-header">Monthly Sales Overview</div>
              <div class="card-body">
                <!-- Include a chart component or library here -->
                <canvas id="salesChart"></canvas>
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
/* Add your custom styles here */
.card {
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.card-header {
  font-weight: bold;
}

.card-body i {
  color: #007bff;
}

.card-body a {
  margin-top: 10px;
}
</style>