<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import Tabs from './shared/Tabs.svelte';

	// tabs
	let items = ['Current Polls', 'Add New Poll'];
	let activeItem = 'Current Polls';

	const onTabChange = (e) => {
		activeItem = e.detail;
	}
</script>

<Header />
<main>
	<Tabs {items} {activeItem} on:tabChange={onTabChange}/>
	{#if activeItem === 'Current Polls'}
		<p>Poll list component</p>
	{:else if activeItem === 'Add New Poll'}
		<p>Poll form component</p>
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>
