<script>
let photo_num = 66;
let curr_photo = "";
let mobile = (window.screen.availWidth <= 600) ? true : false;

const show_high_quality = (e) => {
    if (curr_photo == e.target.src){
        curr_photo = "";
        if (mobile) e.target.classList.remove('zoom');
    }else{
        if (mobile){
            let imgs = document.getElementsByTagName('img');
            [...imgs].forEach(element => {
                element.classList.remove('zoom');
            });
            e.target.classList.add('zoom');
        }
        curr_photo = e.target.src;
    }
}

const remove_curr_photo = (e) => {
    curr_photo = "";
}

const remove_artist_notes = (e) => {
    e.target.classList.add('no_show');
}
</script>

<div id="main_container">
    {#if curr_photo != '' && !mobile}
        <div id="high_res_img">
            <img src={curr_photo} alt={curr_photo} on:click={remove_curr_photo}/>
            <div id="artist_notes" on:click={remove_artist_notes}>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut semper ullamcorper dui vel ornare. Suspendisse placerat id justo ut faucibus. Aenean at leo nisi. Nullam pharetra, orci vitae imperdiet cursus, ipsum libero pulvinar lacus, et vulputate elit nunc in tellus. In libero dui, interdum eget ligula et, semper molestie lacus. In viverra sagittis lorem, eget lobortis tellus bibendum sit amet. Pellentesque non dapibus orci, ut interdum nisi. Cras et porttitor diam, sit amet blandit mauris. Duis ullamcorper egestas leo vel eleifend. Praesent malesuada leo vel orci pulvinar mollis. Nam tellus risus, luctus ac nulla in, auctor rutrum turpis. Nam suscipit accumsan quam, et sollicitudin mi feugiat at. Donec rutrum, leo nec dignissim posuere, augue arcu tincidunt mi, non pretium nisi ante nec magna.
            </div>
        </div>
    {/if}
    {#each Array(photo_num) as _, i}
        <div class="img_container">
            <img src="https://mergeconflict.s3.us-east-2.amazonaws.com/photos/fall_2021/0{i}.jpg" alt="0{i}.jpg" on:click={show_high_quality}/>
            {#if curr_photo == "https://mergeconflict.s3.us-east-2.amazonaws.com/photos/fall_2021/0"+i+".jpg" && mobile}
                <div id="mobile_artist_notes" on:click={remove_artist_notes}>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut semper ullamcorper dui vel ornare. Suspendisse placerat id justo ut faucibus. Aenean at leo nisi. Nullam pharetra, orci vitae imperdiet cursus, ipsum libero pulvinar lacus, et vulputate elit nunc in tellus. In libero dui, interdum eget ligula et, semper molestie lacus. In viverra sagittis lorem, eget lobortis tellus bibendum sit amet. Pellentesque non dapibus orci, ut interdum nisi. Cras et porttitor diam, sit amet blandit mauris. Duis ullamcorper egestas leo vel eleifend. Praesent malesuada leo vel orci pulvinar mollis. Nam tellus risus, luctus ac nulla in, auctor rutrum turpis. Nam suscipit accumsan quam, et sollicitudin mi feugiat at. Donec rutrum, leo nec dignissim posuere, augue arcu tincidunt mi, non pretium nisi ante nec magna.
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
        background-image: url("https://img.freepik.com/free-photo/paperboard-yellow-texture_95678-83.jpg?w=2000&t=st=1654837256~exp=1654837856~hmac=a18a311909ed65cab61c2a0c17f9fcd81d5bcc8aede39d731b5a2ea2d75b735a");
        opacity: 90%;
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
        background-image: url("https://img.freepik.com/free-photo/paperboard-yellow-texture_95678-83.jpg?w=2000&t=st=1654837256~exp=1654837856~hmac=a18a311909ed65cab61c2a0c17f9fcd81d5bcc8aede39d731b5a2ea2d75b735a");
        opacity: 90%;
        position:relative;
        color: rgb(22, 22, 187);
        background-color: beige;
        padding: 7px 15px;
        border: 1px solid black;
        border-radius: 10px;
        bottom: 50px;
        margin: 0px 2%;
    }

    :global(.zoom) {
        transform: scale(3);
    }

    :global(.no_show) {
        display: none;
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