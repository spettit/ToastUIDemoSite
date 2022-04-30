<script>
	import { getStores, navigating, page, session, updated } from '$app/stores';
	$: console.log($page.url.pathname);
</script>

<section>
	<div id="logo">
		<a href="/"><h1>Toastie</h1></a>
	</div>
	<div id="top-bar">
		<h2>Welcome to the Toastie Demo Site</h2>
	</div>
	<nav>
		<a href="/pickers" class:active={$page.url.pathname == '/pickers'}>pickers</a>
		<a href="/editor" class:active={$page.url.pathname == '/editor'}>editor</a>
		<a href="/charts" class:active={$page.url.pathname == '/charts'}>charts</a>
	</nav>
	<container>
		<slot />
	</container>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: 200px 1fr;
		grid-template-rows: 60px 1fr;
		height: 100vh;
	}

	container {
		margin-left: 20px;
	}

	nav {
		background-color: pink;
		display: flex;
		flex-direction: column;
	}

	#logo {
		background-color: pink;
	}

	#top-bar {
		margin-left: 20px;
	}

	nav a {
		margin-top: 10px;
		padding-left: 10px;
		font-weight: bold;
	}

	h1 {
		color: white;
		margin-left: 10px;
	}

	.active {
		color: red;
	}
</style>
