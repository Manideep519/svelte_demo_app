<script lang="ts">
  import { Navbar, NavBrand, NavUl, NavHamburger, Button } from "flowbite-svelte";
  import LogoIcon from "flowbite-svelte-icons/LightbulbOutline.svelte";
</script>

<Navbar class="py-0" let:hidden let:toggle>
  <NavBrand href="/">
    <LogoIcon size="xl" />
    <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"> Super </span>
  </NavBrand>
  <NavHamburger on:click={toggle} />
  <NavUl>
    <Button href="/demo-dashboard" color="alternative">demo-dashboard</Button>
    <Button href="/login" color="alternative">Login</Button>
    <Button href="/register">Register</Button>
  </NavUl>
</Navbar>
<hr />
