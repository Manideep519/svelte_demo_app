<script lang="ts">
  import { Footer, FooterCopyright, FooterLinkGroup, FooterLink } from "flowbite-svelte";
</script>

<Footer class="bg-primary-700 px-8 py-4 flex justify-between">
  <FooterCopyright aClass="text-white" spanClass="text-white" href="/" year={2024} />
  <FooterLinkGroup
    ulClass="flex flex-wrap items-center mt-3 text-sm text-white dark:text-gray-400 sm:mt-0"
  >
    <FooterLink href="/">About</FooterLink>
    <FooterLink href="/">Privacy Policy</FooterLink>
    <FooterLink href="/">Contact</FooterLink>
  </FooterLinkGroup>
</Footer>
