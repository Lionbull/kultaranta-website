<script lang="ts">
    import FaQuestion from 'svelte-icons/fa/FaQuestion.svelte'

    export let title: string;
    export let description: string;

</script>

<div class="feature-wrapper">
    <div class="icon-container">
        <div class="icon">
            <slot>
                <FaQuestion />
            </slot>
        </div>
    </div>
    <h3>{title ? title : "Title"}</h3>
    <p>{description ? description : "Just some description text"}</p>
</div>

<style lang="scss">
    .feature-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
        margin-top: 20px;
    }

    .icon-container {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 70px;
        height: 70px;
    }

    .icon {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0;
    }

    h3 {
        font-weight: 700;
        margin: 0;
    }

    p {
        text-align: center;
        margin: 0 20px;
        line-height: 20px;
    }

</style>