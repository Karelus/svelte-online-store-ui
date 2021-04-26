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

    const handleEmptyButtonClick = () => {
        totalAmount = 0.0;
    };

</script>

<style>
    .emptyButton {
        background-color: red;
        border: none;
        color: white;
        padding: 8px 16px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 12px;
        margin: 4px 2px;
        transition-duration: 0.4s;
        cursor: pointer;
    }
</style>

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
    <p>Total amount: {totalAmount} €</p>
    {#if totalAmount > 0}
        <button class="emptyButton" on:click={handleEmptyButtonClick}>Empty Cart</button>
    {/if}
</div>