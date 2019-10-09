<script>
  export let controlType;
  export let id;
  export let label;
  export let rows;
  export let value;
  export let type;
</script>

<div class="form-group">
  <label for={id}>{label}</label>

  {#if controlType === 'textarea'}
    <textarea
      {rows}
      class="form-control"
      {id}
      placeholder="Enter a description"
      {value}
      on:input />
  {:else}
    <input
      {type}
      class="form-control"
      {id}
      aria-describedby="title"
      placeholder="Enter title"
      {value}
      on:input />
  {/if}

</div>
