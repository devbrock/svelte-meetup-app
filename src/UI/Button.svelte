<script>
  export let type;
  export let caption;
  export let background;
  export let textcolor;
  export let href;
</script>

{#if href}
  <button {type} class="btn btn-{background} text-{textcolor}">
    <a {href} class="text-{textcolor}">{caption}</a>
  </button>
{:else}
  <button {type} class="btn btn-{background} text-{textcolor} " on:click>
    {caption}
  </button>
{/if}
