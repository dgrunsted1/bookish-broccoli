<script>
let photo_num = 66;
let curr_photo = "";

const show_high_quality = (e) => {
    curr_photo = e.target.src;
}

const remove_curr_photo = (e) => {
    curr_photo = "";
}
</script>

<div id="main_container">
    {#if curr_photo != ''}
        <div id="high_res_img">
            <img src={curr_photo} alt={curr_photo} on:click={remove_curr_photo}/>
        </div>
    {/if}
    {#each Array(photo_num) as _, i}
        <div class="img_container">
            <img src="https://mergeconflict.s3.us-east-2.amazonaws.com/photos/fall_2021/0{i}.jpg" alt="0{i}.jpg" on:click={show_high_quality}/>
        </div>
    {/each}
</div>




<style>

    #main_container {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items:center;
        justify-content: center;
    }

    .img_container{
        flex-shrink: 3;
        flex-grow: 0;
    }

    #high_res_img {
        position: fixed;
        top: 50%;
        left: 50%;
        height: 95%;
        transform: translate(-50%, -50%);
    }
    #high_res_img > img {
        height: 100%;
    }

    .img_container > img {
        width: 95%;
        border-radius: 10px;
        transition: transform .5s;
    }


    .img_container > img:hover {
        /* width: 250px; */
        transform: scale(1.1)
    }

    @media only screen and (min-width: 600px) {
        .img_container {
            max-width: 200px;
        }
    }


</style>