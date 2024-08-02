<script lang="ts">

</script>
<div class="main-screen">
    <div class="welcome-image">
        <div class="left-section">
            <h1 class="title">Hyperframe - Wireframe Kit for Figma</h1>
            <p>With our library, you won't spend much time on a prototype. Focus on UX instead of creating standard elements.</p>
            <button class="button-book-now">Book now</button>
        </div>
    </div>
</div>

<style lang="scss">
.main-screen {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90vh;
    width: 100%;
}

.welcome-image {
    margin: 30px;
    width: 100vw;
    height: 85vh;
    background-color: gray;
}

.left-section {
    margin-left: 70px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: left;
    width: 50%;
    height: 100%;

    .title {
        font-size: 45px;
        margin-bottom: 20px;
        font-weight: 500;
    }

    p {
        font-size: 22px;
        margin-bottom: 20px;
    }
    
    .button-book-now {
        background-color: blue;
        color: white;
        height: 50px;
        width: 150px;
        border: none;
        border-radius: 25px;
        cursor: pointer;
    }
}
</style>