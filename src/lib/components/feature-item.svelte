<script lang=ts>
    import FaQuestion from 'svelte-icons/fa/FaQuestion.svelte'

</script>

<div class="feature-wrapper">
    <div class="icon-container">
        <div class="icon">
            <slot>
                <FaQuestion />
            </slot>
        </div>
    </div>
    <h2>Подзаголовок</h2>
    <p>Используйте 1 предложение в 1-3 строчки</p>
</div>

<style>
    .feature-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
        margin-top: 20px;
    }

    .icon-container {
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: bisque;
        border-radius: 50%;
        width: 50px;
        height: 50px;
        margin-bottom: 15px;
    }

    .icon {
        width: 60%;
        height: 60%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    h2 {
        font-weight: 700;
        margin: 0;
        margin-bottom: 10px;
    }

    p {
        text-align: center;
        margin: 0 20px;
        line-height: 20px;
        color: #434343;
    }

</style>