<script>
	import Header from './components/Header.svelte';
    import FilterableProductsTable from './components/FilterableProductsTable.svelte';

	const PRODUCTS = [
    { price: 49.99, stocked: true, name: 'Sneakers'},
    { price: 9.99, stocked: true, name: 'Baseball Cap'},
    { price: 29.99, stocked: false, name: 'Hoodie'},
    { price: 69.99, stocked: true, name: 'Joggers'},
    { price: 79.99, stocked: false, name: 'Volleyball'},
    { price: 29.99, stocked: true, name: 'Sweatpants'},
    { price: 25.99, stocked: true, name: 'Shorts'},
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