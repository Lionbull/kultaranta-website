<script lang="ts">
    import FeatureItem from "./feature-item.svelte";
    import FaFish from 'svelte-icons/fa/FaFish.svelte';
</script>


<div class="content-wrapper">
    <h1>Features</h1>
    <div class="features-wrapper">
        <FeatureItem>
            <FaFish />
        </FeatureItem>

        <FeatureItem>
        </FeatureItem>

        <FeatureItem>
        </FeatureItem>

        <FeatureItem>
        </FeatureItem>

        <FeatureItem>
        </FeatureItem>

        <FeatureItem>
        </FeatureItem>
    </div>
</div>

<style>
    .content-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
    }

    h1 {
        font-weight: 700;
        margin: 0;
    }

    p {
        text-align: center;
        margin: 0 300px;
        line-height: 20px;
    }

    .features-wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
        margin: 10px 75px;
    }

</style>