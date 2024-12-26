<script lang="ts">
import { onMount } from "svelte";

import FaEnvelope from 'svelte-icons/fa/FaEnvelope.svelte'
import FaPhone from 'svelte-icons/fa/FaPhone.svelte'
import FaMapMarkerAlt from 'svelte-icons/fa/FaMapMarkerAlt.svelte'


function initMap() {
    let dumbo = {lat: 61.522782, lng:28.27441};
    let mapOptions = {
        center: dumbo,
        zoom: 7,
        
    };
    let mapElement = document.getElementById("map");
    if (mapElement) {
        let googlemap = new google.maps.Map(mapElement, mapOptions);
        let marker = new google.maps.Marker({
            position: new google.maps.LatLng(61.522782, 28.36441),
            map: googlemap
        });
    }
}
onMount(() => {
    initMap();
});

</script>

<div class="contact-wrapper" id="contacts">
    <h1 class="mobile">Contacts</h1>
    <div class="text-container mobile">
        <div class="text-item">
            <div class="icon">
                <FaMapMarkerAlt />
            </div>
            <p>Kultarannantie 35, 52200 Puumala</p>
        </div>
        <div class="text-item">
            <div class="icon">
                <FaPhone />
            </div>
            <a href="tel:+358456043575">+358 45 604 3575</a>
        </div>
        <div class="text-item">
            <div class="icon">
                <FaEnvelope />
            </div>
            <a href="mailto:saimaan.kultaranta@yahoo.com">saimaan.kultaranta@yahoo.com</a>
        </div>
    </div>
    <div class="contact-content desktop">
        <h2>Contacts</h2>
        <p>Kultarannantie 35, 52200 Puumala</p>
        <p>+358456043575</p>
        <p>saimaan.kultaranta@yahoo.com</p>
    </div>
    <div id="map" />
</div>

<style lang="scss">

    .contact-wrapper {
        .desktop {
            display: flex;
        }

        .mobile {
            display: none;
        }
    }

    #map {
        width: 100svw;
        height: 75vh;
        background-color: grey;
        margin-bottom: 100px;
    }

    .contact-content {
        position: absolute;
        display: flex;
        flex-direction: column;
        transform: translate(5%, 90%);
        background-color: white;
        padding: 25px 30px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        z-index: 9999;
    }

    h2 {
        font-weight: 700;
        margin: 0;
        margin-bottom: 30px;
    }

    p, a {
        margin: 0;
        margin-bottom: 20px;
    }

    @media (max-width: 768px) {
        .contact-wrapper {

            .desktop {
                display: none;
            }

            .mobile {
                display: flex;
            }

            h1 {
                display: flex;
                justify-content: center;
            }
        }

        .text-container {
            display: flex;
            flex-direction: column;
            align-items: left;
            padding: 0 20px;
            gap: 20px;
            margin-bottom: 24px;

            .text-item {
                display: flex;
                align-items: center;
                gap: 10px;

                .icon {
                    width: 19px;
                    height: 19px;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                }
            }

            p, a {
                margin: 0;
                font-size: 15px;
            }

            a {
                color: black;
                text-decoration: underline;
            }
        }


        #map {
            width: 100vw;
            height: 50vh;
            margin-bottom: 60px;
        }

        .contact-content {
            transform: translate(5%, 80%);
        }
    }
    
</style>
