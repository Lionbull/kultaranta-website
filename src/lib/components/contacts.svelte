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
    <h1>Contacts</h1>
    <div class="text-container">
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
    <div id="map" />
</div>

<style lang="scss">
    .contact-wrapper {
        h1 {
            display: flex;
            justify-content: center;
            margin: 0;
        }
    }

    #map {
        width: 100svw;
        height: 75vh;
        background-color: grey;
        margin-bottom: 100px;
    }

    .text-container {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        padding: 0 120px;
        gap: 60px;
        margin: 60px 0 40px 0;

        .text-item {
            display: flex;
            width: auto;
            align-items: center;
            gap: 10px;

            .icon {
                width: 20px;
                height: 20px;
                display: flex;
                align-items: center;
                justify-content: center;
            }
        }

        p, a {
            margin: 0;
        }

        a {
            color: black;
            text-decoration: underline;
        }
    }

    p, a {
        margin: 0;
        margin-bottom: 20px;
    }

    @media (max-width: 768px) {
        .text-container {
            display: flex;
            flex-direction: column;
            align-items: start;
            padding: 0 20px;
            gap: 20px;
            margin: 20px 0 30px 0;

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
        }


        #map {
            width: 100vw;
            height: 50vh;
            margin-bottom: 60px;
        }
    }
    
</style>
