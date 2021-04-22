<script>
    import ProductsTable from './ProductsTable.svelte';
    import SearchBar from './SearchBar.svelte';

    export let products;
    let inStockOnly = false;
    let filterText = '';
    let totalAmount = 0.0;

    const handleFilterTextChange = value => {filterText = value};
    const handleInStockChange = checked => {inStockOnly = checked};

    const handleTotalAmountUpdate = amount => {
        let currentAmount = parseFloat(totalAmount);
        currentAmount += amount;
        currentAmount = Math.round(currentAmount * 100) / 100;
        totalAmount = currentAmount;
    };

</script>

<div class="productTableContainer">
    <SearchBar 
        filterText={filterText}
        inStockOnly={inStockOnly}
        onInputChange={handleFilterTextChange}
        onInStockChange={handleInStockChange} 
    />
    <ProductsTable
        products={products}
        filterText={filterText}
        inStockOnly={inStockOnly}
        onAmountUpdate={handleTotalAmountUpdate}
    />
    <p>{totalAmount} €</p>
    {#if totalAmount > 0}
        <button>Empty Cart</button>
    {/if}
</div>