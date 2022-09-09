<script>
  export let controlType;
  export let id;
  export let label;
  export let rows;
  export let value;
</script>

<div class="form-control">
  <label for={id}>{label}</label>
  {#if controlType === "textaread"}
    <input type="text" {id} placeholder="set subtitle" {value} on:input />
  {:else}
    <textarea {rows} {id} placeholder="set description" {value} on:input />
  {/if}
</div>
