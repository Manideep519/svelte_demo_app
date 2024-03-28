<script lang="ts">
  import "../app.pcss";
  import NavBar from "$lib/components/NavBar/+page.svelte";
  import Footer from "$lib/components/Footer/+page.svelte";
</script>

<NavBar />
<div class="min-h-[calc(100vh-130px)] flex items-center justify-center">
  <slot />
</div>
<Footer />
