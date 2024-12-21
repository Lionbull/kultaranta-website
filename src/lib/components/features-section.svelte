<script lang="ts">
    import FeatureItem from "./feature-item.svelte";
    import { base } from "$app/paths";

</script>


<div class="content-wrapper">
    <h1>Features</h1>
    <div class="features-wrapper">
        <FeatureItem
            title="Private Sauna"
            description="Each cottage is equipped with private sauna"
        >
            <img src="{base}/sauna-icon.png" alt="Sauna" style="width: 65px; height: 65px;">
        </FeatureItem>

        <FeatureItem
            title="Fishing"
            description="Great opportunities for fishing in Saimaa lake"
        >
            <img src="{base}/fish-icon.png" alt="Fishing" style="width: 70px; height: 70px;">
        </FeatureItem>

        <FeatureItem
            title="BBQ"
            description="Private BBQ at each cottage and local BBQ spots"
        >
        <img src="{base}/bbq-icon.png" alt="BBQ" style="width: 55px; height: 70px;">
        </FeatureItem>

        <FeatureItem
            title="Boating"
            description="Boats available free of costto enjoy the views of Saimaa or fishing"
        >
            <img src="{base}/boating-icon.png" alt="Boating" style="width: 70px; height: 55px;">
        </FeatureItem>

        <FeatureItem
            title="Beach"
            description="Each cottage is equipped with private sauna"
        >
            <img src="{base}/beach-icon.png" alt="Beach" style="width: 70px; height: 70px;">
        </FeatureItem>

        <FeatureItem
            title="Pet Friendly"
            description="Pets are welcome at Saimaan Kultaranta"
        >
            <img src="{base}/pet-icon.png" alt="Pet Friendly" style="width: 70px; height: 70px;">
        </FeatureItem>
    </div>
</div>

<style>
    .content-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
        box-sizing: border-box;
        padding: 0 120px;
        margin: 0 0 100px 0;
    }

    h1 {
        font-weight: 700;
        margin: 0;
    }

    .features-wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
    }

</style>