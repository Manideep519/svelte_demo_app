<script lang="ts">
  import Stats from "$lib/components/Stats/+page.svelte";
  import PokeTable from "$lib/components/PokeTable/+page.svelte";
  import MapBox from "$lib/components/MapBox/+page.svelte";
  import { P } from "flowbite-svelte";

  export let view = "";

  let DashboardMap = {
    Stats,
    Pokemon: PokeTable,
  };
</script>

<div class="overflow-y-auto rounded dark:bg-gray-800 bg-white flex-1 self-stretch p-8 w-full">
  {#if view === "Stats"}
    <Stats />
  {:else if view === "Pokemon"}
    <PokeTable />
  {:else if view === "Map"}
    <MapBox />
  {:else}
    <h3>View not found</h3>
  {/if}
</div>
