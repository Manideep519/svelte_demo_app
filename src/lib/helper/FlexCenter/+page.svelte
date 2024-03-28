<script lang="ts">
  export let css: string;
</script>

<div class={`flex justify-center items-center ${css}`}>
  <slot />
</div>
