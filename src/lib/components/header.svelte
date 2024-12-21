<script lang="ts">
	import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'
</script>

<header>
	<div class="logo">
		<div class="image">
			<img src="/cirle-logo.png" alt="logo" />
		</div>
	</div>

	<div class="menu">
		<div>Cottages</div>
		<div>Features</div>
		<div>About Us</div>
		<div>Contacts</div>
	</div>

	<div class="button-wrapper">
		<div class="button">
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