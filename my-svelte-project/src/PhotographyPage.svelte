<script>
let photo_num = 66;
</script>

<div id="main_container">
    {#each Array(photo_num) as _, i}
        <div class="img_container">
            <img src="https://mergeconflict.s3.us-east-2.amazonaws.com/photos/fall_2021/0{i}.jpg" alt="0{i}.jpg"/>
            <div>
                <p>
                    photographers notes will go here.
                </p>
            </div>
        </div>
    {/each}
</div>



<style>

    #main_container {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items:center;
        justify-content: space-between;
    }

    .img_container{
        flex-shrink: 3;
        flex-grow: 0;
        max-width: 550px;
    }
    img {
        width: 95%;
        border-radius: 10px;
        border: 1px solid black;
    }


</style>