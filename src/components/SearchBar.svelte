<script>

  export let filterText;
  export let inStockOnly;
  export let onInputChange;
  export let onInStockChange;

  let handleInputChange = e => {onInputChange(e.target.value)};
  let handleInStockChange = e => {onInStockChange(e.target.checked)};

</script>

<style>

</style>

<form>
    <input type=text placeholder="Search..." bind:value={filterText} on:input={handleInputChange} />
    <p>
      <input type=checkbox bind:checked={inStockOnly} on:change={handleInStockChange} />
      {' '}
            Only show products in stock
    </p>
</form>