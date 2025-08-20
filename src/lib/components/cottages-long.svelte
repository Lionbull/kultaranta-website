<script lang="ts">
    import FaUserAlt from 'svelte-icons/fa/FaUserAlt.svelte'
    import PhotoGallery from './photo-gallery.svelte';
    import { base } from '$app/paths';
    import { goto } from '$app/navigation';

    let imagesCottageBig = [
        `${base}/area-photo-1.webp`,
        `${base}/area-photo-2.webp`,
        `${base}/area-photo-3.webp`,
        `${base}/area-photo-4.webp`,
        `${base}/area-photo-5.webp`,
        `${base}/area-photo-6.webp`,
        `${base}/area-photo-7.webp`,
        `${base}/area-photo-8.webp`,
    ];

    let imagesCottageSmall = [
        `${base}/area-photo-1.webp`,
        `${base}/area-photo-2.webp`,
        `${base}/area-photo-3.webp`,
        `${base}/area-photo-4.webp`,
        `${base}/area-photo-5.webp`,
        `${base}/area-photo-6.webp`,
        `${base}/area-photo-7.webp`,
        `${base}/area-photo-8.webp`,
    ];

</script>

<div class="content-wrapper" id="cottages">
    <h1>Cottages</h1>
    <div class="cottage-container">
        <div class="big-cottage">
            <div class="upper-section">
                <div class="image">
                    <img src="{base}/big-cottage-overview.webp" alt="Big Cottage">
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
                        <button class="button-read-more" on:click={() => window.open(`https://www.booking.com/hotel/fi/saimaan-kultaranta.en-gb.html?aid=898224&label=hotel_details-hs6QC5G%401734886622&sid=b9e93e10d90fa9624ff05b9f407e3ced&checkin=2025-05-01&checkout=2025-05-02&dest_id=-1382891&dest_type=city&dist=0&do_availability_check=1&group_adults=2&group_children=0&hp_avform=1&hp_group_set=0&no_rooms=1&origin=hp&sb_price_type=total&src=hotel&type=total&#availability_target`, "_blank")}>
                            Book now
                        </button>
                    </div>
                </div>
            </div>
            <div class="lower-section">
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
            </div>
            <div class="image-section">
                <PhotoGallery images={imagesCottageBig} />
            </div>
        </div>
        <div class="separator" />
        <div class="small-cottage">
            <div class="upper-section">
                <div class="image">
                    <img class="small" src="{base}/small-cottage-overview.webp" alt="Small Cottage">
                </div>
                <div class="text-content right">
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
                                <img src="{base}/area-icon.svg" alt="area">
                            </div>
                            <p>60 m²</p>
                        </div>
                        <div class="info-item">
                            <div class="info-icon">
                                <img src="{base}/sauna-icon.png" alt="area">
                            </div>
                            <p>Private sauna</p>
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <button class="button-read-more" on:click={() => window.open(`https://www.booking.com/hotel/fi/saimaan-kultaranta.en-gb.html?aid=898224&label=hotel_details-hs6QC5G%401734886622&sid=b9e93e10d90fa9624ff05b9f407e3ced&checkin=2025-05-01&checkout=2025-05-02&dest_id=-1382891&dest_type=city&dist=0&do_availability_check=1&group_adults=2&group_children=0&hp_avform=1&hp_group_set=0&no_rooms=1&origin=hp&sb_price_type=total&src=hotel&type=total&#availability_target`, "_blank")}>
                            Book now
                        </button>
                    </div>
                </div>
            </div>
            <div class="lower-section">
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliquaLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
            </div>
            <div class="image-section">
                <PhotoGallery images={imagesCottageSmall} />
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
    margin: 100px 0 100px 0;

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
        gap: 80px;

        .separator {
            height: 2px;
            width: 60%;
            background-color: #737373;
            border-radius: 15px;
        }

        .big-cottage {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .small-cottage {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .upper-section {
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
                    transition: box-shadow 0.250s;

                    &:hover {
                        box-shadow: 0 0 30px rgba(104, 112, 88, 0.5);
                    }
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
                border-radius: 30px;
            }

            .small {
                object-position: 100% 100%;
            }
        }

        .lower-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
            margin: 40px 0 40px 0;

            p {
                text-align: left;
                margin: 0;
            }
        }

        .image-section {
            width: 100%;
            height: 100%;
        }
    }
}

@media (max-width: 768px) {
    .content-wrapper {
        padding: 0 20px;
        margin: 0 0 60px 0;

        h1 {
            margin: 60px 0 30px 0;
        }

        p {
            font-size: 14px;
            margin: 0 20px;
        }

        .cottage-container {
            gap: 30px;

            .big-cottage {
                flex-direction: column;
            }

            .separator {
                display: block;
                width: 160px;
                height: 2px;
                background-color: #737373;
                border-radius: 30px;
                margin: 30px 0;
            }

            .small-cottage {
                flex-direction: column;
            }

            .upper-section {
                flex-direction: column;
                gap: 20px;
            }

            .text-content {
                width: 100%;

                .button-wrapper {
                    justify-content: center;

                    .button-read-more {
                        width: 202px;
                        height: 57px;
                        font-size: 16px;
                    }
                }
            }

            .text-content.right {
                padding-left: 0;
            }

            .text-content.left {
                padding-right: 0;
            }

            .image {
                width: 335px;
                height: 229px;

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

            .lower-section {
                margin: 20px 0 20px 0;
            }
        }
    }
}
</style>