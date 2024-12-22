<script lang="ts">
    import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'
    import { base } from '$app/paths';

</script>
<div class="main-screen">
    <div class="welcome-image" style="background-image: url('{base}/road-to-kultaranta.webp');">
        <div class="left-section">
            <h1 class="title">Discover Serinity<br>at Saimaan Kultaranta</h1>
            <p>Owned and operated by a local family, Saimaan Kultaranta invites you to enjoy a peaceful getaway with thoughtful amenities and warm hospitality. Discover a unique retreat where nature and comfort come together.</p>
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <!-- svelte-ignore a11y-no-static-element-interactions -->
            <div class="button" on:click={() => window.open(`https://www.booking.com/hotel/fi/saimaan-kultaranta.en-gb.html?aid=898224&label=hotel_details-hs6QC5G%401734886622&sid=b9e93e10d90fa9624ff05b9f407e3ced&checkin=2025-05-01&checkout=2025-05-02&dest_id=-1382891&dest_type=city&dist=0&do_availability_check=1&group_adults=2&group_children=0&hp_avform=1&hp_group_set=0&no_rooms=1&origin=hp&sb_price_type=total&src=hotel&type=total&#availability_target`, "_blank")}>
                <p class="button-text">
                    Book now
                </p>
                <div class="button-icon">
                    <FaRegCalendarAlt/>
                </div>
            </div>
        </div>
    </div>
</div>

<style lang="scss">
.main-screen {
    height: calc(100vh - 100px);
    width: 100vw;
    overflow-x: hidden;
}

.welcome-image {
    display: flex;
    align-items: center;
    overflow-x: hidden;
    width: 100vw;
    height: 100%;
    background-size: 100% 100%;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
}

.left-section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: left;
    background-color: rgba(238, 232, 214, 0.84);
    width: 35%;
    margin-left: 120px;
    gap: 22px;
    border-radius: 50px;
    padding: 40px 48px;

    .title {
        font-family: 'Montserrat', serif;
        font-size: 48px;
        font-weight: bold;
        line-height: 1.25;
        margin: 0;
    }

    p {
        line-height: 1.6;
        font-size: 20px;
        margin: 0;
    }
    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 150px;
        background-color: #687058;
        color: white;
        border-radius: 80px;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.30);
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