<script>

  export let filterText;
  export let inStockOnly;
  export let onInputChange;
  export let onInStockChange;

  let handleInputChange = e => {onInputChange(e.target.value)};
  let handleInStockChange = e => {onInStockChange(e.target.checked)};

</script>

<style>
  
  form {
    display: flex;
    flex-direction: column;
  }
  
  .searchBar {
    border-radius: 10px !important;
    border: none;
    margin-top: 20px;
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
</style>

<form>
    <input class="searchBar" type=text placeholder="Search..." bind:value={filterText} on:input={handleInputChange} />
    <p>
      <input type=checkbox bind:checked={inStockOnly} on:change={handleInStockChange} />
      {' '}
            Only show products in stock
    </p>
</form>