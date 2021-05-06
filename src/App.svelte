<script>
	import Header from './components/Header.svelte';
    import FilterableProductsTable from './components/FilterableProductsTable.svelte';

	const PRODUCTS = [
    { price: 49.99, stocked: true, name: 'Sneakers'},
    { price: 9.99, stocked: true, name: 'Baseball Cap'},
    { price: 29.99, stocked: false, name: 'Hoodie'},
    { price: 69.99, stocked: true, name: 'Training Joggers'},
    { price: 19.99, stocked: false, name: 'Training Shirt'},
    { price: 29.99, stocked: true, name: 'Sweatpants'},
    { price: 25.99, stocked: true, name: 'Training Shorts'},
  	];

</script>

<style>
	.container {
		display: flex;
  		flex-wrap: wrap;
  		flex-direction: row;
  		justify-content: space-evenly;
	}
</style>

<main class="container">
	<Header />
	<FilterableProductsTable products={PRODUCTS} />
</main>