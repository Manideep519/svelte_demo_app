<script lang="ts">
  import "../app.pcss";
  import NavBar from "$lib/components/NavBar/+page.svelte";
  import Footer from "$lib/components/Footer/+page.svelte";
</script>

<NavBar />
<slot />
<Footer />
