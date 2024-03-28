<script>
  import { Section, HeroHeader } from "flowbite-svelte-blocks";
  import { Button } from "flowbite-svelte";
  import { ArrowRightOutline } from "flowbite-svelte-icons";
  import HeroPortrait from "$lib/assets/images/hero_.jpg";
</script>

<Section sectionClass="py-0" name="heroVisual">
  <div class="mr-auto place-self-center lg:col-span-7">
    <HeroHeader
      h1Class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white"
      pClass="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 md:text-lg lg:text-xl dark:text-gray-400"
    >
      <svelte:fragment slot="h1">Super tool for software companies</svelte:fragment>
      <svelte:fragment slot="paragraph"
        >From checkout to global sales tax compliance, companies around the world use Super to
        simplify their development stack.</svelte:fragment
      >
      <a href="/login"
        ><Button size="xl" color="primary" class="inline-flex items-center justify-center mr-3"
          >Get started<ArrowRightOutline size="md" class="ml-2 -mr-1" /></Button
        >
      </a>
      <a href="/about"
        ><Button color="light" size="xl" class="inline-flex items-center justify-center"
          >Learn more</Button
        >
      </a>
    </HeroHeader>
  </div>
  <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
    <img src={HeroPortrait} alt="Super" />
  </div>
</Section>
