<script lang="ts">
	import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'
	import IoIosMenu from 'svelte-icons/io/IoIosMenu.svelte'
	import FaHome from 'svelte-icons/fa/FaHome.svelte'
	import FaStar from 'svelte-icons/fa/FaStar.svelte'
	import FaQuoteRight from 'svelte-icons/fa/FaQuoteRight.svelte'
	import FaPhone from 'svelte-icons/fa/FaPhone.svelte'
	import FaEnvelope from 'svelte-icons/fa/FaEnvelope.svelte'
	import FaMapMarkerAlt from 'svelte-icons/fa/FaMapMarkerAlt.svelte'
	import { base } from '$app/paths';
	import { goto } from '$app/navigation';
	
	let isMobileMenuOpen = false;
	
	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}
	
	function closeMobileMenu() {
		isMobileMenuOpen = false;
	}
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
		<!-- TODO: Remove test from the url as soon as the website is ready -->
		<div on:click={() => goto(`${base}/cottages`)}>Cottages</div>
		<div on:click={() => goto(`${base}/test#features`)}>Features</div>
		<div on:click={() => goto(`${base}/test#reviews`)}>Reviews</div>
		<div on:click={() => goto(`${base}/test#contacts`)}>Contacts</div>
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

	<!-- Mobile menu -->

	<div class="menu-button-wrapper">
		<button class="hamburger" on:click={toggleMobileMenu}>
			<div class="button-icon">
				<IoIosMenu />
			</div>
		</button>
	</div>

	{#if isMobileMenuOpen}
		<div class="mobile-menu-overlay" on:click={closeMobileMenu}></div>
	{/if}

	<nav class="menu-mobile" class:open={isMobileMenuOpen}>
		<button class="close-btn" on:click={closeMobileMenu}>✕</button>
		<ul class="menu-list">
		  <li>
		  	<a href="{base}/cottages" on:click={closeMobileMenu}>
		  		<div class="menu-icon"><FaHome /></div>
		  		<span>Cottages</span>
		  	</a>
		  </li>
		  <!-- TODO: Remove test from the url as soon as the website is ready -->
		  <li>
		  	<a href="{base}/test#features" on:click={closeMobileMenu}>
		  		<div class="menu-icon"><FaStar /></div>
		  		<span>Features</span>
		  	</a>
		  </li>
		  <li>
		  	<a href="{base}/test#reviews" on:click={closeMobileMenu}>
		  		<div class="menu-icon"><FaQuoteRight /></div>
		  		<span>Reviews</span>
		  	</a>
		  </li>
		  <li>
		  	<a href="{base}/test#contacts" on:click={closeMobileMenu}>
		  		<div class="menu-icon"><FaPhone /></div>
		  		<span>Contacts</span>
		  	</a>
		  </li>
		</ul>
		
		<div class="contact-section">
			<div class="contact-header">Contact Us</div>
			<div class="contact-items">
				<div class="contact-item">
					<div class="contact-icon"><FaMapMarkerAlt /></div>
					<span>Kultarannantie 35, 52200 Puumala</span>
				</div>
				<div class="contact-item">
					<div class="contact-icon"><FaPhone /></div>
					<a href="tel:+358456043575">+358 45 604 3575</a>
				</div>
				<div class="contact-item">
					<div class="contact-icon"><FaEnvelope /></div>
					<a href="mailto:saimaan.kultaranta@yahoo.com">saimaan.kultaranta@yahoo.com</a>
				</div>
			</div>
		</div>
	</nav>
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

	.menu-button-wrapper {
		display: none;
	}

	.mobile-menu-overlay {
		display: none;
	}

	.menu-mobile {
		display: none;
	}

	@media (max-width: 768px) {
		header {
			height: 70px;
			padding: 0 20px;
		}
		.logo {
			display: flex;
			align-items: center;

			.image {
				width: 53px;
				height: 50px;
				
				img {
					width: 100%;
					height: 100%;
				}
			}
		}

		.menu {
			display: none;
		}

		.button-wrapper {
			display: none;
		}

		.menu-button-wrapper {
			display: flex;
			align-items: center;
			justify-content: center;
			width: 46px;
			margin: 0;
			padding: 0;

			.hamburger {
				width: 46px;
				height: 46px;
				margin: 0;
				padding: 0;
				font-size: 2rem;
				color: white;
				background: none;
				border: none;
				cursor: pointer;
				transition: all 0.2s ease;

				&:hover {
					opacity: 0.8;
				}

				.button-icon {
					width: 46px;
					height: 46px;
					margin: 0;
					padding: 0;
				}
			}
		}

		.mobile-menu-overlay {
			position: fixed;
			top: 0;
			left: 0;
			width: 100vw;
			height: 100vh;
			background-color: rgba(0, 0, 0, 0.5);
			display: block;
			z-index: 998;
		}

		.menu-mobile {
			position: fixed;
			top: 0;
			right: 0;
			width: 280px;
			height: 100vh;
			background: linear-gradient(135deg, #687058 0%, #5a6349 100%);
			display: flex;
			flex-direction: column;
			align-items: flex-start;
			padding: 0;
			box-sizing: border-box;
			transform: translateX(100%);
			transition: transform 0.25s cubic-bezier(0.25, 0.46, 0.45, 0.94);
			z-index: 999;
			box-shadow: -5px 0 20px rgba(0, 0, 0, 0.3);

			&.open {
				transform: translateX(0);
			}

			.close-btn {
				align-self: flex-end;
				width: 50px;
				height: 50px;
				padding: 0;
				margin: 20px 20px 0 0;
				font-size: 1.8rem;
				color: white;
				background: rgba(255, 255, 255, 0.1);
				border: none;
				border-radius: 50%;
				cursor: pointer;
				transition: all 0.2s ease;
				display: flex;
				align-items: center;
				justify-content: center;

				&:hover {
					background: rgba(255, 255, 255, 0.2);
					transform: scale(1.05);
				}
			}

			.menu-list {
				list-style: none;
				padding: 30px 0 20px 0;
				width: 100%;
				margin: 0;
				flex: 1;

				li {
					width: 100%;
					border-bottom: 1px solid rgba(255, 255, 255, 0.1);

					&:last-child {
						border-bottom: none;
					}

					a {
						display: flex;
						align-items: center;
						padding: 20px 15px;
						color: white;
						text-decoration: none;
						font-size: 1.2rem;
						font-weight: 500;
						transition: all 0.2s ease;
						border-left: 4px solid transparent;
						gap: 15px;

						&:hover {
							background: rgba(255, 255, 255, 0.1);
							border-left-color: #EEE8D6;
							padding-left: 35px;
						}

						.menu-icon {
							width: 20px;
							height: 20px;
							display: flex;
							align-items: center;
							justify-content: center;
							flex-shrink: 0;
						}

						span {
							flex: 1;
						}
					}
				}
			}

			.contact-section {
				padding: 20px 10px 30px 20px;
				border-top: 1px solid rgba(255, 255, 255, 0.2);
				background: rgba(0, 0, 0, 0.1);
				width: 100%;
				box-sizing: border-box;

				.contact-header {
					color: white;
					font-size: 1.1rem;
					font-weight: 600;
					margin-bottom: 15px;
					text-align: left;
				}

				.contact-items {
					display: flex;
					flex-direction: column;
					gap: 12px;

					.contact-item {
						display: flex;
						align-items: flex-start;
						gap: 10px;
						font-size: 0.9rem;
						width: 100%;
						min-width: 0; // Allows flex items to shrink below their content size

						.contact-icon {
							width: 16px;
							height: 16px;
							color: #EEE8D6;
							flex-shrink: 0;
							margin-top: 1px; // Align with first line of text
						}

						span, a {
							color: rgba(255, 255, 255, 0.9);
							text-decoration: none;
							font-size: 0.8rem;
							line-height: 1.4;
							word-wrap: break-word;
							word-break: break-word;
							overflow-wrap: break-word;
							flex: 1;
							min-width: 0;
						}

						a {
							&:hover {
								color: #EEE8D6;
								text-decoration: underline;
							}
						}
					}
				}
			}
		}
	}

</style>