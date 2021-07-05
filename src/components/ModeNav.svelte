<script lang="ts">
	export let mode: 'overview' | 'internal' | 'geology';
	export let name: string;
	export let changeMode: (mode: string) => {};
	let passedClass: 'desktop-menu' | 'mobile-menu';
	export { passedClass as class };
</script>

<nav class={`nav-container ${passedClass || ''}`}>
	<ul>
		<li class={mode === 'overview' ? name : ''} on:click={() => changeMode('overview')}>
			<span class="desktop-display">01 </span>OVERVIEW
		</li>
		<li class={mode === 'internal' ? name : ''} on:click={() => changeMode('internal')}>
			<span class="desktop-display">02 INTERNAL</span> STRUCTURE
		</li>
		<li class={mode === 'geology' ? name : ''} on:click={() => changeMode('geology')}>
			<span class="desktop-display">03 SURFACE</span> GEOLOGY
		</li>
	</ul>
</nav>

<style>
	nav {
		margin-top: 39px;
	}
	ul {
		padding: 0px;
		list-style: none;
	}
	li {
		font-family: 'Spartan', sans-serif;
		font-weight: bold;
		cursor: pointer;
	}
	.desktop-menu li {
		border: 1px solid #979797;
		margin-bottom: 16px;
		padding: 12px 28px;
	}
	.mobile-menu ul {
		display: grid;
		grid-auto-flow: column;
	}
	.mobile-menu li {
		font-size: 9px;
	}
	.mobile-menu .desktop-display {
		display: none;
	}

	/* planet specific styling */
	.desktop-menu .Mercury {
		background-color: #419ebb;
		border: none;
		cursor: default;
	}

	.desktop-menu .Venus {
		background-color: #eda249;
		border: none;
		cursor: default;
	}

	.desktop-menu .Earth {
		background-color: #6d2ed5;
		border: none;
		cursor: default;
	}

	.desktop-menu .Mars {
		background-color: #d14c32;
		border: none;
		cursor: default;
	}

	.desktop-menu .Jupiter {
		background-color: #d83a34;
		border: none;
		cursor: default;
	}

	.desktop-menu .Saturn {
		background-color: #cd5120;
		border: none;
		cursor: default;
	}

	.desktop-menu .Uranus {
		background-color: #1ec1a2;
		border: none;
		cursor: default;
	}

	.desktop-menu .Neptune {
		background-color: #2d68f0;
		border: none;
		cursor: default;
	}
	/* responsive breakpoints */

	/* phone */
	@media (max-width: 500px) {
		nav {
			margin-top: 0px;
			border-bottom: 1px solid #979797;
			padding: 20px 0px;
		}
		.desktop-menu {
			display: none;
		}
	}

	/* tablet */
	@media (min-width: 651px) {
		li {
			font-size: 9px;
		}
		.mobile-menu {
			display: none;
		}
	}

	/* computer */
	@media (min-width: 801px) {
		li {
			font-size: 12px;
		}
	}
</style>
