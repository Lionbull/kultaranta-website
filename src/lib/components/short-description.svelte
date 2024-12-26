<script lang="ts">
</script>

<div class="desc-wrapper">
    <div class="separator-upper" />
    <p>Experience the perfect lakeside escape at Saimaan Kultaranta, where cozy cottages, private saunas, and breathtaking views of Saimaa await. Relax, recharge, and create unforgettable memories amidst the beauty of South Savo's nature.</p>
    <div class="separator-lower" />
</div>

<style lang="scss">

.desc-wrapper {
    margin: 100px 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.separator-upper, .separator-lower {
    height: 5px;
    width: 175px;
    background-color: #737373;
    border-radius: 15px;
}

.separator-upper {
    margin: 0 0 30px 0;
}

.separator-lower {
    margin: 30px 0 0 0;
}

p {
    text-align: center;
    width: 65vw;
    margin: 0 50px;
    font-size: 22px;
    font-weight: 500;
    line-height: 50px;
}

@media (max-width: 768px) {
    .desc-wrapper {
        margin: 60px 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .separator-upper, .separator-lower {
        height: 2px;
        width: 130px;
        background-color: #737373;
        border-radius: 15px;
    }

    .separator-upper {
        margin: 0 0 20px 0;
    }

    .separator-lower {
        margin: 20px 0 0 0;
    }

    p {
        text-align: center;
        box-sizing: border-box;
        width: 100%;
        margin: 0;
        padding: 0 20px;
        font-size: 14px;
        font-weight: 500;
        line-height: 165%;
    }
}

</style>