<script lang="ts">
    import FaRegCalendarAlt from 'svelte-icons/fa/FaRegCalendarAlt.svelte'
    import { base } from '$app/paths';

</script>
<div class="main-screen">
    <div class="welcome-image" style="background-image: url('{base}/road-to-kultaranta.jpg');">
        <div class="left-section">
            <h1 class="title">Discover Serinity<br>at Saimaan Kultaranta</h1>
            <p>Owned and operated by a local family, Saimaan Kultaranta invites you to enjoy a peaceful getaway with thoughtful amenities and warm hospitality. Discover a unique retreat where nature and comfort come together.</p>
            <div class="button">
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
    height: 89.5vh;
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
    margin-left: 100px;
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