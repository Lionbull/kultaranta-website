<script lang="ts">
</script>

<header>
	<div class="logo">
		<div class="image"></div>
		<div class="text">Logo</div>
	</div>

	<div class="menu">
		<div>Features</div>
		<div>Price</div>
		<div>About us</div>
		<div>Contacts</div>
	</div>

	<div class="button-wrapper">
		<button class="button-book-now">Book now</button>
	</div>

</header>

<style lang="scss">
	header {
		display: flex;
		justify-content: space-between;
		background-color: gray;
		height: 60px;
		margin: 0;
		padding: 0 100px;
	}

	.logo {
		display: flex;
		align-items: center;

		.image {
			width: 30px;
			height: 30px;
			background-color: blue;
		}
	}

	.text {
		margin-left: 20px;
		font-size: 25px;
		color: blue;
	}

	.menu {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 20px;

		div {
			margin: 0 10px;
			font-size: 15px;
		}
	}

	.button-wrapper {
		display: flex;
		align-items: center;
		justify-content: center;

		.button-book-now {
			background-color: blue;
			color: white;
			height: 35px;
			width: 100px;
			border: none;
			border-radius: 25px;
			cursor: pointer;
		}
	}

</style>