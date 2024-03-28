<script lang="ts">
  import LineChart from "$lib/components/Stats/LineChart/+page.svelte";
  import AreaChart from "$lib/components/Stats/AreaChart/+page.svelte";
  import DonutChart from "$lib/components/Stats/DonutChart/+page.svelte";
  import FlexCenter from "$lib/helper/FlexCenter/+page.svelte";
</script>

<FlexCenter css="items-stretch gap-3">
  <LineChart />
  <AreaChart />
  <DonutChart />
</FlexCenter>
