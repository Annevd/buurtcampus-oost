<script>
	import { AgendaCarousel } from '$lib/index.js';
	import AgendaInfoButton from '$lib/molecules/agenda-info-button.svelte';
	export let data;
</script>

<section>
	<img src="./assets/mistletoe.png" alt="" height="800" width="800" />
	<h2>Agenda</h2>
	<AgendaInfoButton />
	<AgendaCarousel {data} />
</section>

<style>
	section {
		background: var(--main-color-beige);
		z-index: 2;
		max-width: 100%;
		overflow: hidden;
		padding: 4rem 0 4rem 1rem;
		position: relative;
	}

	img {
		display: none;
		position: absolute;
		rotate: 85deg;
		/* left: 6rem;
		bottom: 3rem; */
		transform: rotateZ(180deg) scale(0.5);
		right: -15rem;
		top: -14rem;
		mix-blend-mode: hard-light;
		opacity: 75%;
	}

	h2 {
		font-size: 3.5rem;
		padding-bottom: 0.7em;
		font-family: var(--sub-header-font);
		color: #fff;
		align-self: baseline;
		z-index: 10;
	}

	/* MEDIA QUERY TABLET = 768px */
	@media (min-width: 48rem) {
		section {
			padding: 4rem 0 4rem 7.5rem;
		}

		h2 {
			font-size: 4.5rem;
		}
		img {
			display: block;
		}
	}

	/* MEDIA QUERY DESKTOP = 1500px */
	@media (min-width: 93.75rem) {
		/* section {
			padding: 4rem 15em;
		} */
	}
</style>
