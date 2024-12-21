<script lang="ts">
    import FaWhatsapp from 'svelte-icons/fa/FaWhatsapp.svelte'
    import FaInstagram from 'svelte-icons/fa/FaInstagram.svelte'

    let currentYear = new Date().getFullYear()
</script>

<footer>
    <div class="logo">
		<div class="image"></div>
		<div class="text">Logo</div>
	</div>

    <div class="icon-container">
        <div class="icon">
            <FaWhatsapp />
        </div>
        <div class="icon">
            <FaInstagram />
        </div>
    </div>

    <div class="copyright">© {currentYear} Saimaan Kultaranta</div>

</footer>

<style lang="scss">
    footer {
        display: flex;
        flex-direction: column;
        justify-content: center;
        text-align: center;
        background-color: #f0f0f0;
        padding: 40px;
        gap: 30px;
    }

    .logo {
		display: flex;
		align-items: center;
        justify-content: center;

		.image {
			width: 30px;
			height: 30px;
			background-color: blue;
		}
	}

    .text {
		margin-left: 20px;
		color: blue;
	}

    .icon-container {
        display: flex;
        justify-content: center;
        gap: 20px;
        padding: 0;
        margin: 0;
    }

    .icon {
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        width: 30px;
        height: 30px;
        margin-bottom: 15px;
        padding: 0;
        margin: 0;
    }

    .copyright {
        color: #434343;
        margin: 0;
    }
</style>