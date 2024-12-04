<script lang="ts">
	let words = [
		'Private Equity',
		'Private Debt',
		'Private Funds',
		'ESG and Sustainability',
		'Alternatives'
	];
	let currentIndex = 0;

	// Change the word every 2 seconds (1.5 seconds for staying + 0.5 seconds for transition)
	setInterval(() => {
		currentIndex = (currentIndex + 1) % words.length;
	}, 2000);
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section class="relative w-full">
	<!-- <h1>
		<span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcomeFallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app
	</h1>

	<h2>
		try editing <strong>src/routes/+page.svelte</strong>
	</h2>

	<Counter /> -->
	<video
		autoplay
		muted
		loop
		class="w-full"
		src="https://kldx.com/wp-content/themes/kapital-dx/videos/newvideo2.mp4"
	>
		<track kind="captions" />
	</video>
	<div
		class="absolute left-1/2 top-1/2 flex w-full -translate-x-1/2 -translate-y-1/2 transform flex-col items-center justify-center"
	>
		<h1 class="leading-tight text-white">Expand your<br />Investment Universe</h1>
		<p class="mt-1 text-white">
			A secure, trusted platform that empowers your private market investments.
		</p>
		<p class="mt-4 text-white">Tap into the power of investing directly</p>
		<div class="mt-4 flex items-center justify-center">
			{#each words as word, index (word)}
				<span
					class={`absolute font-semibold text-white opacity-0 ${index === currentIndex ? 'word-enter visible' : 'hidden'}`}
				>
					{word}
				</span>
			{/each}
		</div>
	</div>
</section>

<style>
	.word-enter {
		animation: scrollUp 2s ease-in-out forwards;
	}

	@keyframes scrollUp {
		0% {
			opacity: 0;
			transform: translateY(50%);
		}
		25% {
			opacity: 1;
			transform: translateY(0);
		}
		75% {
			opacity: 1;
			transform: translateY(0);
		}
		100% {
			opacity: 0;
			transform: translateY(-50%);
		}
	}
</style>
