<script>
    import Product from './Product.svelte';

    export let products;
    export let filterText;
    export let inStockOnly;
    export let onAmountUpdate;
</script>

<style>
    table {
        background-color: #F0F3FF;
        padding: 10px;
        border-radius: 5px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
        margin: auto; 
    }
</style>

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
