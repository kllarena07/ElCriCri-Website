<script lang="ts">
  export let themeNumber : number
  export let selectedTheme : number
</script>

{#if selectedTheme === themeNumber}
  <slot></slot>
{/if}