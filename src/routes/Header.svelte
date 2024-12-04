<script lang="ts">
	import logoFallback from '$lib/images/logo.png';
	import logo from '$lib/images/logo.webp';
	import '../app.css';

	let isIcon1Visible = $state(true);

	const toggleIcon = () => {
		isIcon1Visible = !isIcon1Visible;
	};
</script>

<header class="h-20 bg-[#f2fbfe] px-6">
	<div class="flex w-full items-center justify-between">
		<a href="https://kldx.com">
			<picture>
				<source srcset={logo} type="image/webp" />
				<img src={logoFallback} alt="Logo" class="h-6" />
			</picture>
		</a>
		<div class="flex flex-row items-center gap-3">
			<button
				type="button"
				class="w-32 rounded border-[1px] border-solid border-black bg-white px-4 py-2 hover:bg-gray-200"
			>
				Login
			</button>
			<button
				type="button"
				class="flex w-32 flex-row justify-between rounded border-[1px] border-solid border-black bg-gradient-to-b from-[#0C226F] to-[#2255E2] py-2 pl-8 pr-2 text-white hover:bg-gradient-to-b hover:from-[#1A3BA2] hover:to-[#3B6DF5]"
			>
				Sign Up
				<svg
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 24 24"
					stroke-width="1.5"
					stroke="currentColor"
					class="mt-[0.2rem] size-5"
				>
					<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
				</svg>
			</button>
			<button onclick={toggleIcon} aria-label="bars-icon">
				{#if isIcon1Visible}
					<svg
						id="icon-bars"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
						class="ml-4 size-9"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
						/>
					</svg>
				{/if}
				{#if !isIcon1Visible}
					<svg
						id="icon-x"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
						class="ml-4 size-9"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
					</svg>
				{/if}
			</button>
		</div>
	</div>
	<!-- <div class="corner">
		<a href="https://svelte.dev/docs/kit">
			<img src={logo} alt="SvelteKit" />
		</a>
	</div> -->

	<nav>
		<!-- <svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
		</svg>
		<ul class="mt-10 h-10">
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
			<li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Sverdle</a>
			</li>
		</ul>
		<svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
		</svg> -->
	</nav>

	<!-- <div class="corner">
		<a href="https://github.com/sveltejs/kit">
			<img src={github} alt="GitHub" />
		</a>
	</div> -->
</header>

<style lang="postcss">
	header {
		display: flex;
		justify-content: space-between;
	}

	/* .corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	} */

	nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
	}

	/* svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: var(--background);
	} */

	/* ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	} */
</style>
