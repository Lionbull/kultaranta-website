<script lang="ts">
  import { onMount } from "svelte";


function initMap() {
    let dumbo = {lat: 61.522782, lng:28.27441};
    let mapOptions = {
        center: dumbo,
        zoom: 12,
        
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

<div class="contact-wrapper">
    <div class="contact-content">
        <h2>Contacts</h2>
        <p>Kultarannantie 35, 52200 Puumala</p>
        <p>+358456043575</p>
        <p>saimaan.kultaranta@yahoo.com</p>
    </div>
    <div id="map" />
</div>

<style>
    #map {
        width: 100vw;
        height: 70vh;
        background-color: grey;
        margin-bottom: 50px;
    }

    .contact-content {
        position: absolute;
        transform: translate(40%, 40%);
        background-color: white;
        padding: 40px 50px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        z-index: 9999;
    }

    h2 {
        font-size: 2rem;
        font-weight: 700;
        margin: 0;
        margin-bottom: 30px;
    }

    p {
        font-size: 1.05rem;
        margin: 0;
        margin-bottom: 20px;
    }
    
</style>
