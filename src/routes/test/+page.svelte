<script lang="ts">
	import Header from "../../lib/components/header.svelte";
	import WelcomeScreen from "../../lib/components/welcome-screen.svelte";
	import ShortDescription from "../../lib/components/short-description.svelte";
	import Cottages from "../../lib/components/cottages.svelte";
	import PhotoGallery from "../../lib/components/photo-gallery.svelte";
  	import FeaturesSection from "../../lib/components/features-section.svelte";
	import ReviewCards from "../../lib/components/review-cards.svelte";
    import Contacts from "$lib/components/contacts.svelte";
    import Footer from "$lib/components/footer.svelte";
</script>

<Header />
<WelcomeScreen />
<ShortDescription />
<Cottages />
<PhotoGallery />
<FeaturesSection />
<ReviewCards />
<Contacts />
<Footer />