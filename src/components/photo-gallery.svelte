<script lang="ts">

</script>

<div class="gallery-wrapper">
    <div class="image-type1"></div>
    <div class="image-type2"></div>
    <div class="image-type1"></div>
    <div class="image-type2"></div>
    <div class="image-type2"></div>
    <div class="image-type1"></div>
    <div class="image-type2"></div>
    <div class="image-type1"></div>
</div>

<style lang="scss">

.gallery-wrapper {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(2, 1fr);
    gap: 5px;
    margin: 50px 0;

    .image-type1 {
        width: calc(25vw - 4px);
        height: calc(25vw - 4px);
        background-color: gray;
    }

    .image-type2 {
        width: calc(25vw - 4px);
        height: calc(25vw - 4px);
        background-color: lighten(gray, 30%);
    }
}
</style>