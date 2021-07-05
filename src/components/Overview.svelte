<script lang="ts">
	import PlanetImage from './PlanetImage.svelte';
	import ModeNav from './ModeNav.svelte';
	export let image: string;
	export let name: string;
	export let content: string;
	export let source: string;
	export let changeMode: (mode: string) => {};
	export let mode: 'overview' | 'internal' | 'geology';
	export let secondImage: string | null;
</script>

<div class="planet-container">
	<!-- Menu for mobile -->
	<ModeNav class="mobile-menu" {name} {changeMode} {mode} />
	<div class="image-container">
		<PlanetImage {name} {image} {secondImage} />
	</div>
	<div class="description-container">
		<div>
			<h1>{name}</h1>
			<p>{content}</p>
			<span>
				Source :
				<a href={source} target="blank">Wikapedia</a>
			</span>
		</div>

		<!-- Menu for tablet and desktop -->
		<ModeNav class="desktop-menu" {name} {changeMode} {mode} />
	</div>
</div>

<style>
	h1 {
		font-family: 'Antonio', sans-serif;
		font-weight: 500;
		margin-bottom: 23px;
	}
	p {
		font-family: 'Spartan', sans-serif;
		margin-bottom: 24px;
	}
	span {
		font-family: 'Spartan', sans-serif;
	}

	.image-container {
		margin-top: 20px;
		width: 100%;
		display: grid;
		justify-content: center;
	}

	.planet-container {
		text-align: center;
		padding: 24px;
		display: grid;
		justify-content: center;
		align-items: center;
	}
	.description-container {
		max-width: 350px;
		text-align: left;
	}

	/* responsive breakpoints */

	/* phone */
	@media (max-width: 500px) {
		h1 {
			font-size: 40px;
		}
		p {
			font-size: 11px;
			line-height: 22px;
		}
		.planet-container {
			grid-auto-flow: row;
			gap: 0px;
			padding: 0px;
			justify-content: normal;
		}
		.image-container {
			margin-bottom: 85px;
		}
		.description-container {
			text-align: center;
			margin: auto;
		}
	}

	/* tablet */
	@media (min-width: 651px) {
		h1 {
			font-size: 40px;
		}
		p {
			font-size: 11px;
			line-height: 22px;
		}
		.planet-container {
			grid-auto-flow: row;
			gap: 100px;
			padding: 24px 39px;
		}
		.description-container {
			display: grid;
			grid-template-columns: repeat(2, minmax(0, 1fr));
			max-width: 100%;
			gap: 60px;
			align-items: center;
		}
	}

	/* computer */
	@media (min-width: 801px) {
		h1 {
			font-size: 80px;
		}
		p {
			font-size: 14px;
			line-height: 25px;
		}
		.planet-container {
			grid-auto-flow: column;
			gap: 220px;
		}
		.description-container {
			display: grid;
			grid-template-columns: repeat(1, minmax(0, 1fr));
			max-width: 350px;
			gap: 39px;
		}
	}
</style>
