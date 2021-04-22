<script>
    import Product from './Product.svelte';

    export let products;
    export let filterText;
    export let inStockOnly;
    export let onAmountUpdate;
</script>

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Price</th>
        </tr>
    </thead>
    <tbody>
        {#each products as product}
            {#if product.name.indexOf(filterText) === -1}
                <!-- Skips iteration -->
            {:else if inStockOnly && !product.stocked}
                <!-- Skips iteration -->
            {:else}
                <Product name={product.name}
                price={product.price}
                stocked={product.stocked}
                onAddButtonClick={onAmountUpdate}
                />
           {/if}
        {/each}
    </tbody>
</table>
