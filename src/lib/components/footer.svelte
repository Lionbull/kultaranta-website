<script lang="ts">
    import FaWhatsapp from 'svelte-icons/fa/FaWhatsapp.svelte'
    import FaInstagram from 'svelte-icons/fa/FaInstagram.svelte'
    import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'

    let currentYear = new Date().getFullYear()
</script>

<footer>
    <div class="logo">
		<div class="image">
			<img src="/cirle-logo.png" alt="logo" />
		</div>
	</div>

    <div class="contacts">
        <p>+358456043575</p>
		<p>Kultarannantie 35, 52200 Puumala</p>
		<p>saimaan.kultaranta@yahoo.com</p>
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
        background-color: #687058;
        padding: 60px;
        gap: 40px;
    }

    .logo {
		display: flex;
		align-items: center;
        justify-content: center;

		.image {
			width: 87px;
			height: 81px;
			
			img {
				width: 100%;
				height: 100%;
			}
		}
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
        color: white;
    }

    .copyright {
        color: white;
        margin: 0;
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

    .contacts {
        display: flex;
        flex-direction: column;
        color: white;
        gap: 20px;
        p {
            margin: 0;
        }
    }
</style>