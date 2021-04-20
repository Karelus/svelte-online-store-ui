<script>
    import ProductsTable from './ProductsTable.svelte';
    import SearchBar from './SearchBar.svelte';

    export let products;

    let totalAmount = 0;

</script>

<!-- <style>
	.productTableContainer {
		width: 30%;
        height: auto;
        margin-top: 30px;
	}

</style> -->

<div class="productTableContainer">
    <SearchBar />
    <ProductsTable products={products} />
    <p>0 €</p>
    <!-- Conditional rendering -->
    {#if totalAmount > 0}
    <button>Empty Cart</button>
    {/if}
</div>