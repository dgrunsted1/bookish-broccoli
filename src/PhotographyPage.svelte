<script>
let photo_num = 66;
let curr_photo = "";
let mobile = (window.screen.availWidth <= 600) ? true : false;

const show_high_quality = (e) => {

    if (curr_photo == e.target.src) curr_photo = "";
    else curr_photo = e.target.src;
    console.log({curr_photo});
}

const remove_curr_photo = (e) => {
    curr_photo = "";
}
</script>

<div id="main_container">
    {#if curr_photo != '' && !mobile}
        <div id="high_res_img">
            <img src={curr_photo} alt={curr_photo} on:click={remove_curr_photo}/>
            <div id="artist_notes">
                artists notes will go here
            </div>
        </div>
    {/if}
    {#each Array(photo_num) as _, i}
        <div class="img_container">
            <img src="https://mergeconflict.s3.us-east-2.amazonaws.com/photos/fall_2021/0{i}.jpg" alt="0{i}.jpg" on:click={show_high_quality}/>
            {#if curr_photo == "https://mergeconflict.s3.us-east-2.amazonaws.com/photos/fall_2021/0"+i+".jpg" && mobile}
                <div id="mobile_artist_notes">
                    artists notes will go here
                </div>
            {/if}
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

    #artist_notes {
        position: fixed;
        bottom: 0;
        left: 50%;
        color: rgb(22, 22, 187);
        transform: translate(-50%, -50%);
        background-color: beige;
        padding: 7px 30px;
        border: 1px solid black;
        border-radius: 10px;
    }

    #mobile_artist_notes{
        position:relative;
        color: rgb(22, 22, 187);
        background-color: beige;
        padding: 7px 15px;
        border: 1px solid black;
        border-radius: 10px;
        bottom: 50px;
        margin: 0px 2%;
    }


    

    @media only screen and (min-width: 600px) {
        .img_container {
            max-width: 200px;
        }
        .img_container > img:hover {
        transform: scale(1.1);
    }
    }


</style>