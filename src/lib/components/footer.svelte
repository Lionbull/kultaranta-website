<script lang="ts">
    import { base } from "$app/paths";
    import { goto } from '$app/navigation';
    import FaWhatsapp from 'svelte-icons/fa/FaWhatsapp.svelte'
    import FaInstagram from 'svelte-icons/fa/FaInstagram.svelte'
    import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'

    let currentYear = new Date().getFullYear()
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<footer>
    <div class="logo">
		<div class="image" on:click={() => goto(`${base}/`)}>
			<img src="{base}/cirle-logo.png" alt="logo" />
		</div>
	</div>

    <div class="contacts">
        <p>Kultarannantie 35, 52200 Puumala</p>
        <a href="tel:+358456043575">+358 45 604 3575</a>
		<a href="mailto:saimaan.kultaranta@yahoo.com">saimaan.kultaranta@yahoo.com</a>
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

    <div class="icon-container">
        <div class="icon" on:click={() => window.open(`https://wa.me/358456043575`, "_blank")}>
            <FaWhatsapp />
        </div>
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
			width: 120px;
			height: 112px;
            cursor: pointer;
			
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
            transition: box-shadow 0.250s;

			&:hover {
				box-shadow: 0 0 20px rgba(238, 232, 214, 0.5);
			}

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
        align-items: center;
        width: auto;
        color: white;
        gap: 20px;

        p, a {
            margin: 0;
            width: auto;
        }

        a {
            color: white;
            text-decoration: underline;
        }
    }
</style>