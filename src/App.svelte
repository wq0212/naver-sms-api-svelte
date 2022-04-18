<script>
	import {Route, Link, Router} from "svelte-routing";
	import Login from './routes/Login.svelte';
	import Join from './routes/Join.svelte';

	export let url = "";
</script>

<Router {url}>
	<nav>
		<Link to="/">Login</Link>
		<Link to="join">Join</Link>
	</nav>
	<div>
		<Route path="/"><Login /></Route>
		<Route path="join"><Join /></Route>
	</div>
</Router>

<main>
</main>

<style>
</style>