<script lang="ts">
	import { base } from "$app/paths";
	import Header from "../../lib/components/header.svelte";
	import WelcomeScreen from "../../lib/components/welcome-screen.svelte";
	import ShortDescription from "../../lib/components/short-description.svelte";
	import CottagesShort from "../../lib/components/cottages-short.svelte";
	import PhotoGallery from "../../lib/components/photo-gallery.svelte";
  	import FeaturesSection from "../../lib/components/features-section.svelte";
	import ReviewCards from "../../lib/components/review-cards.svelte";
    import Contacts from "$lib/components/contacts.svelte";
    import Footer from "$lib/components/footer.svelte";

	const imagesPhotoGallery = [
      `${base}/area-photo-1.webp`,
      `${base}/area-photo-2.webp`,
      `${base}/area-photo-3.webp`,
      `${base}/area-photo-4.webp`,
      `${base}/area-photo-5.webp`,
      `${base}/area-photo-6.webp`,
      `${base}/area-photo-7.webp`,
      `${base}/area-photo-8.webp`,
    ];
</script>

<Header />
<WelcomeScreen />
<ShortDescription />
<CottagesShort />
<div class="photo-gallery-container">
	<PhotoGallery images={imagesPhotoGallery}/>
</div>
<FeaturesSection />
<ReviewCards />
<Contacts />
<Footer />

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Oswald:wght@200..700&display=swap');

	.photo-gallery-container {
		padding: 0 120px;
	}

	:global(body) {
		margin: 0;
		padding: 0;
		background-color: #EEE8D6;
		overflow-x: hidden;
	}

	:global(h1) {
		font-family: "Oswald", serif;
		font-size: 64px;
		color: #1d1d1d;
	}

	:global(h2) {
		font-size: 32px;
		font-family: "Montserrat", serif;
	}

	:global(h3) {
		font-size: 24px;
		font-family: "Montserrat", serif;
	}

	:global(h3, h4, h5, h6) {
		font-family: "Montserrat", serif;
	}

	:global(p, a, li, div) {
		font-family: "Montserrat", serif;
		font-weight: 400;
		font-size: 18px;
		letter-spacing: 0.03rem;
	}

	:global(button) {
		font-family: "Montserrat", serif;
		font-weight: 400;
		font-size: 16px;
	}

	@media (max-width: 768px) {
		.photo-gallery-container {
			padding: 0 20px;
		}

		:global(body) {
			margin: 0;
			padding: 0;
			background-color: #EEE8D6;
		}

		:global(h1) {
			font-family: "Oswald", serif;
			font-size: 32px;
		}

		:global(h2) {
			font-size: 24px;
			font-family: "Montserrat", serif;
		}

		:global(h3) {
			font-size: 22px;
			font-family: "Montserrat", serif;
		}

		:global(h3, h4, h5, h6) {
			font-family: "Montserrat", serif;
		}

		:global(p, li, div) {
			font-family: "Montserrat", serif;
			font-weight: 400;
			font-size: 14px;
			letter-spacing: 0.03rem;
		}

		:global(button) {
			font-family: "Montserrat", serif;
			font-weight: 400;
			font-size: 16px;
		}
	}
</style>