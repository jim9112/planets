<script lang="ts">
	import Overview from '../components/Overview.svelte';
	export let planet: {
		name: string;
		rotation: string;
		revolution: string;
		radius: string;
		temperature: string;
		images: {
			planet: string;
			internal: string;
			geology: string;
		};
		overview: {
			content: string;
			source: string;
		};
		structure: {
			content: string;
			source: string;
		};
		geology: {
			content: string;
			source: string;
		};
	};
	let mode = 'overview';

	const changeMode = (newMode: string): string => (mode = newMode);
</script>

<!-- Change overview display based on the selected mode -->
{#if mode === 'overview'}
	<Overview
		{mode}
		image={planet.images.planet}
		secondImage={null}
		name={planet.name}
		content={planet.overview.content}
		source={planet.overview.source}
		{changeMode}
	/>
{:else if mode === 'internal'}
	<Overview
		{mode}
		image={planet.images.internal}
		secondImage={null}
		name={planet.name}
		content={planet.structure.content}
		source={planet.structure.source}
		{changeMode}
	/>
{:else if mode === 'geology'}
	<Overview
		{mode}
		image={planet.images.planet}
		secondImage={planet.images.geology}
		name={planet.name}
		content={planet.geology.content}
		source={planet.geology.source}
		{changeMode}
	/>
{/if}

<div class="stat-container">
	<div class="stat">
		<h4>ROTATION TIME</h4>
		<span>
			{planet.rotation}
		</span>
	</div>
	<div class="stat">
		<h4>REVOLUTION TIME</h4>
		<span>
			{planet.revolution}
		</span>
	</div>
	<div class="stat">
		<h4>RADIUS</h4>
		<span>
			{planet.radius}
		</span>
	</div>
	<div class="stat">
		<h4>AVERAGE TEMP.</h4>
		<span>
			{planet.temperature}
		</span>
	</div>
</div>

<style>
	h4 {
		font-family: 'Spartan', sans-serif;
		font-weight: bold;
	}
	span {
		font-family: 'Antonio', sans-serif;
		font-weight: 500;
	}
	.stat-container {
		display: grid;
		padding: 56px 40px;
		grid-template-columns: repeat(4, minmax(0, 1fr));
		justify-content: center;
		gap: 30px;
	}
	.stat {
		border: 1px solid #979797;
		display: grid;
		grid-auto-flow: row;
		padding: 23px;
	}

	/* responsive breakpoints */

	/* phone */
	@media (max-width: 650px) {
		.stat-container {
			grid-template-columns: 1fr;
			gap: 8px;
			margin: 0px;
		}
		.stat {
			margin: 0px;
			grid-auto-flow: column;
			padding: 10px 24px;
			align-items: center;
		}
		h4 {
			font-size: 8px;
		}
		span {
			font-size: 20px;
		}
		.stat span {
			justify-self: end;
		}
	}

	/* tablet */
	@media (min-width: 651px) {
		span {
			font-size: 24pxpx;
		}
		h4 {
			font-size: 8px;
		}
	}

	/* computer */
	@media (min-width: 801px) {
		span {
			font-size: 40px;
		}
		h4 {
			font-size: 11px;
		}
	}
</style>
