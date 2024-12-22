<script lang="ts">
	import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'
	import { base } from '$app/paths';
	import { goto } from '$app/navigation';
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<header>
	<div class="logo">
		<div class="image" on:click={() => goto(`${base}/`)}>
			<img src="{base}/cirle-logo.png" alt="logo" />
		</div>
	</div>

	<div class="menu">
		<div on:click={() => goto(`${base}/cottages`)}>Cottages</div>
		<div on:click={() => goto(`${base}/#features`)}>Features</div>
		<div on:click={() => goto(`${base}/#reviews`)}>Reviews</div>
		<div on:click={() => goto(`${base}/#contacts`)}>Contacts</div>
	</div>

	<div class="button-wrapper">
		<div class="button" on:click={() => window.open(`https://www.booking.com/hotel/fi/saimaan-kultaranta.en-gb.html?aid=898224&label=hotel_details-hs6QC5G%401734886622&sid=b9e93e10d90fa9624ff05b9f407e3ced&checkin=2025-05-01&checkout=2025-05-02&dest_id=-1382891&dest_type=city&dist=0&do_availability_check=1&group_adults=2&group_children=0&hp_avform=1&hp_group_set=0&no_rooms=1&origin=hp&sb_price_type=total&src=hotel&type=total&#availability_target`, "_blank")}>
			<p class="button-text">
				Book now
			</p>
			<div class="button-icon">
				<FaRegCalendarAlt/>
			</div>
		</div>
	</div>

</header>

<style lang="scss">
	header {
		display: flex;
		justify-content: space-between;
		background-color: #687058;
		height: 100px;
		margin: 0;
		padding: 0 120px;
		box-shadow: 0 0 4px rgba(0, 0, 0, 0.25);
	}

	.logo {
		display: flex;
		align-items: center;

		.image {
			width: 87px;
			height: 81px;
			cursor: pointer;
			
			img {
				width: 100%;
				height: 100%;
			}
		}
	}

	.menu {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 72px;

		div {
			margin: 0 10px;
			font-weight: 600;
			color: white;
			font-size: 18px;
			cursor: pointer;
		}
	}

	.button-wrapper {
		display: flex;
		align-items: center;
		justify-content: center;

		.button {
			display: flex;
			align-items: center;
			justify-content: center;
			background-color: #EEE8D6;
			border-radius: 80px;
			box-shadow: 0 0 4px rgba(0, 0, 0, 0.25);
			padding: 16px 32px;
			gap: 10px;
			cursor: pointer;

			.button-text {
				margin: 0;
				
			}

			.button-icon {
				width: 20px;
				height: 20px;
			}
		}
	}

</style>