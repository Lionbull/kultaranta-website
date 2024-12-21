<script lang="ts">

</script>

<div class="content-wrapper">
    <h1>Заголовок - о чем блок</h1>
    <p>Описание - основной смысл. Используйте 1-2 предложения в 1-3 строчки, если выравнивание по центру. При большем количестве текста используйте другой тип выравнивания контента</p>

    <div class="small-cottage-container">
        <div class="small-cottage">
            <!-- <img src="images/cottage1.jpg" alt="cottage1"> -->
            <div class="image"></div>
            <div class="right-content">
                <h3>Cottage Type 1</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
                <ul>
                    <li>1 bedroom</li>
                    <li>1 bathroom</li>
                    <li>1 kitchen</li>
                    <li>asdasd</li>
                </ul>
                <div class="button-wrapper">
                    <button class="button-read-more">
                        Read more
                    </button>
                </div>
            </div>
        </div>
        <div class="big-cottage">
            <!-- <img src="images/cottage1.jpg" alt="cottage1"> -->
            <div class="left-content">
                <h3>Cottage Type 2</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</p>
                <ul>
                    <li>1 bedroom</li>
                    <li>1 bathroom</li>
                    <li>1 kitchen</li>
                    <li>asdasd</li>
                </ul>
                <div class="button-wrapper">
                    <button class="button-read-more">
                        Read more
                    </button>
                </div>
            </div>
            <div class="image"></div>
        </div>
    </div>
</div>

<style lang="scss">
.content-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin: 20px 0;

    h1 {
        margin-bottom: 30px;
        font-weight: 600;
    }
    
    p {
        text-align: center;
        margin: 0 325px;
        line-height: 25px;
    }

    .small-cottage {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin: 50px 0;

        .image {
            width: 400px;
            height: 400px;
            background-color: gray;
            margin: 0 20px;
        }

        .right-content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: left;
            width: 400px;
            height: 400px;
            padding-left: 50px;

            h3 {
                margin-bottom: 20px;
                font-weight: 500;
            }

            p {
                text-align: left;
                line-height: 25px;
                margin: 0;
            }
        }
    }

    .big-cottage {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin: 50px 0;

        .image {
            width: 400px;
            height: 400px;
            background-color: gray;
            margin: 0 20px;
        }

        .left-content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: left;
            width: 400px;
            height: 400px;
            padding-right: 30px;
            padding-left: 50px;

            h3 {
                margin-bottom: 20px;
                font-weight: 500;
            }

            p {
                text-align: left;
                line-height: 25px;
                margin: 0;
            }
        }
    }

    ul {
        padding: 0;
        margin: 10px 20px;
        margin-bottom: 20px;

        li {
            margin-bottom: 10px;
        }
    }

    .button-wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0 20px;

        .button-read-more {
            background-color: blue;
            color: white;
            height: 50px;
            width: 200px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
        }
    }
}
</style>