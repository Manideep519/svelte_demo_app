<script lang="ts">
  import DashboardContent from "$lib/components/Dashboard/DashboardContent/+page.svelte";
  import DashboardSidebar from "$lib/components/Dashboard/DashboardSideBar/+page.svelte";
</script>

<div class="p-3">
  <div class="bg-gray-100 container mx-auto p-3">
    <div class="flex gap-3">
      <DashboardSidebar />
      <DashboardContent />
    </div>
  </div>
</div>
