<script lang="ts">
  import Stats from "$lib/components/Stats/+page.svelte";
  import PokeTable from "$lib/components/PokeTable/+page.svelte";
</script>

<div class="overflow-y-auto rounded dark:bg-gray-800 bg-white self-stretch p-8">
  <Stats />
  <PokeTable />
</div>
