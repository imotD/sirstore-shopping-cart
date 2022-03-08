<template>
  <div>
    <Navbar />
    <Dashboard />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Dashboard from "@/components/Dashboard.vue";
export default {
  name: "Home",
  components: {
    Navbar,
    Dashboard,
  },
};
</script>
