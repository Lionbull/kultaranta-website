<script lang="ts">
    import { base } from "$app/paths";
    import FaWhatsapp from 'svelte-icons/fa/FaWhatsapp.svelte'
    import FaInstagram from 'svelte-icons/fa/FaInstagram.svelte'
    import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'

    let currentYear = new Date().getFullYear()
</script>

<footer>
    <div class="logo">
		<div class="image">
			<img src="{base}/cirle-logo.png" alt="logo" />
		</div>
	</div>

    <div class="contacts">
        <p>+358456043575</p>
		<p>Kultarannantie 35, 52200 Puumala</p>
		<p>saimaan.kultaranta@yahoo.com</p>
	</div>

    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div class="button-wrapper">
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div class="button" on:click={() => window.open(`https://www.booking.com/hotel/fi/saimaan-kultaranta.en-gb.html?aid=898224&label=hotel_details-hs6QC5G%401734886622&sid=b9e93e10d90fa9624ff05b9f407e3ced&checkin=2025-05-01&checkout=2025-05-02&dest_id=-1382891&dest_type=city&dist=0&do_availability_check=1&group_adults=2&group_children=0&hp_avform=1&hp_group_set=0&no_rooms=1&origin=hp&sb_price_type=total&src=hotel&type=total&#availability_target`, "_blank")}>
			<p class="button-text">
				Book now
			</p>
			<div class="button-icon">
				<FaRegCalendarAlt/>
			</div>
		</div>
    </div>

    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div class="icon-container">
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div class="icon" on:click={() => window.open(`https://wa.me/358456043575`, "_blank")}>
            <FaWhatsapp />
        </div>
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div class="icon" on:click={() => window.open(`https://www.instagram.com/saimaan_kultaranta`, "_blank")}>
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
        width: 40px;
        height: 40px;
        margin-bottom: 15px;
        padding: 0;
        margin: 0;
        color: white;
        cursor: pointer;
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