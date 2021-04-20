<script>
    import Product from './Product.svelte';

    export let products;
</script>

<!-- <style>
	.productTableContainer {
		width: 30%;
        height: auto;
        margin-top: 30px;
	}

</style> -->

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Price</th>
        </tr>
    </thead>
    <tbody>
        {#each products as product}
        <Product {...product}/>
        {/each}
    </tbody>
</table>
