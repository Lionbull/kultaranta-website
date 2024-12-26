<script lang="ts">
    import FeatureItem from "./feature-item.svelte";
    import { base } from "$app/paths";

</script>


<div class="content-wrapper" id="features">
    <h1>Features</h1>
    <div class="features-wrapper">
        <FeatureItem
            title="Private Sauna"
            description="Each cottage is equipped with private sauna"
        >
            <img id="sauna-icon" src="{base}/sauna-icon.png" alt="Sauna">
        </FeatureItem>

        <FeatureItem
            title="Fishing"
            description="Great opportunities for fishing in Saimaa lake"
        >
            <img id="fishing-icon" src="{base}/fish-icon.png" alt="Fishing">
        </FeatureItem>

        <FeatureItem
            title="BBQ"
            description="Private BBQ at each cottage and local BBQ spots"
        >
        <img id="bbq-icon" src="{base}/bbq-icon.png" alt="BBQ">
        </FeatureItem>

        <FeatureItem
            title="Boating"
            description="Boats available free of cost to enjoy the views of Saimaa or fishing"
        >
            <img id="boating-icon" src="{base}/boating-icon.png" alt="Boating">
        </FeatureItem>

        <FeatureItem
            title="Beach"
            description="Each cottage is equipped with private sauna"
        >
            <img id="beach-icon" src="{base}/beach-icon.png" alt="Beach">
        </FeatureItem>

        <FeatureItem
            title="Pet Friendly"
            description="Pets are welcome at Saimaan Kultaranta"
        >
            <img id="pet-icon" src="{base}/pet-icon.png" alt="Pet Friendly">
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
        margin: 100px 0 100px 0;
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

    #sauna-icon {
        width: 65px;
        height: 65px;
    }

    #fishing-icon {
        width: 70px;
        height: 70px;
    }

    #bbq-icon {
        width: 55px;
        height: 70px;
    }

    #boating-icon {
        width: 70px;
        height: 55px;
    }

    #beach-icon {
        width: 70px;
        height: 70px;
    }

    #pet-icon {
        width: 70px;
        height: 70px;
    }


    @media (max-width: 768px) {
        .content-wrapper {
            padding: 0 20px;
            margin: 60px 0 60px 0;
        }

        .features-wrapper {
            grid-template-columns: repeat(1, 1fr);
            gap: 40px;
        }

        #sauna-icon {
            width: 52px;
            height: 46px;
        }

        #fishing-icon {
            width: 54px;
            height: 48px;
        }

        #bbq-icon {
            width: 47px;
            height: 55px;
        }

        #boating-icon {
            width: 53px;
            height: 36px;
        }

        #beach-icon {
            width: 53px;
            height: 49px;
        }

        #pet-icon {
            width: 51px;
            height: 49px;
        }
    }

</style>