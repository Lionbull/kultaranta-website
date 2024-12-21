<script lang="ts">
    import FaUserAlt from 'svelte-icons/fa/FaUserAlt.svelte'
    import { base } from '$app/paths';

</script>

<div class="content-wrapper">
    <h1>Cottages</h1>
    <div class="cottage-container">
        <div class="big-cottage">
            <div class="image">
                <img src="{base}/big-cottage-overview.jpg" alt="Big Cottage">
            </div>
            <div class="text-content right">
                <h2>Three-Bedroom Villa</h2>
                <p>Spacious and cozy, our Big Cottages feature a private sauna, a fireplace, a large terrace, and BBQ facilities, perfect for families or groups seeking ultimate comfort by the lake.</p>
                <div class="cottage-info">
                    <div class="info-item">
                        <div class="info-icon">
                            <FaUserAlt />
                        </div>
                        <p>5 (+2) Guests</p>
                    </div>
                    <div class="info-item">
                        <div class="info-icon">
                            <img src="{base}/area-icon.svg" alt="Area">
                        </div>
                        <p>80 m²</p>
                    </div>
                    <div class="info-item">
                        <div class="info-icon">
                            <img src="{base}/sauna-icon.png" alt="Sauna">
                        </div>
                        <p>Private sauna</p>
                    </div>
                </div>
                <div class="button-wrapper">
                    <button class="button-read-more">
                        Read more
                    </button>
                </div>
            </div>
        </div>
        <div class="small-cottage">
            <div class="text-content left">
                <h2>Standard Villa</h2>
                <p>Charming and intimate, our Small Cottages offer a private sauna, a fireplace, and a cozy terrace with BBQ, ideal for couples or smaller groups looking for a peaceful retreat.</p>
                <div class="cottage-info">
                    <div class="info-item">
                        <div class="info-icon">
                            <FaUserAlt />
                        </div>
                        <p>4 (+2) Guests</p>
                    </div>
                    <div class="info-item">
                        <div class="info-icon">
                            <img src="/area-icon.svg" alt="area">
                        </div>
                        <p>60 m²</p>
                    </div>
                    <div class="info-item">
                        <div class="info-icon">
                            <img src="/sauna-icon.png" alt="area">
                        </div>
                        <p>Private sauna</p>
                    </div>
                </div>
                <div class="button-wrapper">
                    <button class="button-read-more">
                        Read more
                    </button>
                </div>
            </div>
            <div class="image">
                <img class="small" src="{base}/small-cottage-overview.jpg" alt="Small Cottage">
            </div>
        </div>
    </div>
</div>

<style lang="scss">
.content-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0 120px;
    margin: 0 0 100px 0;

    h1 {
        margin: 0 0 60px 0;
        font-weight: 600;
    }

    p {
        text-align: center;
        margin: 0 325px;
        line-height: 25px;
    }

    .cottage-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
        gap: 65px;

        .big-cottage {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: 20px;
        }

        .small-cottage {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: 20px;
        }

        .text-content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: left;
            box-sizing: border-box;
            width: 50%;
            gap: 24px;

            h2 {
                font-weight: 500;
                margin: 0;
            }

            p {
                text-align: left;
                line-height: 25px;
                margin: 0;
            }

            .cottage-info {
                padding: 0;
                margin: 0;

                .info-item {
                    display: flex;
                    flex-direction: row;
                    margin-bottom: 10px;
                    gap: 15px;

                    .info-icon {
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        width: 25px;
                        height: 25px;

                        img {
                            width: 100%;
                            height: 100%;
                        }
                    }
                }
            }

            .button-wrapper {
                display: flex;
                justify-content: left;
                align-items: center;

                .button-read-more {
                    background-color: #687058;
                    color: white;
                    height: 68px;
                    width: 285px;
                    border: none;
                    border-radius: 50px;
                    font-size: 18px;
                    font-weight: 500;
                    cursor: pointer;
                }
            }
        }

        .text-content.right {
            padding-left: 7%;
        }

        .text-content.left {
            padding-right: 7%;
        }

        .image {
            width: 50%;
            height: 45vh;

            img {
                width: 100%;
                height: 100%;
                object-fit: cover;
                border-radius: 35px;
            }

            .small {
                object-position: 100% 100%;
            }
        }
    }
}
</style>