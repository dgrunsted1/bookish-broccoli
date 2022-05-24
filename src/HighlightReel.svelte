<script>
    let links = [   {"title": "Allen Iverson", "link": "https://www.youtube.com/embed/13YeR5zIGbo?start=60&autoplay=1&mute=1", "text": "Standing just 6-feet tall, Allen Iverson became one of the most lethal scorers in NBA history. While he was frequently the smallest player on the court, he could get anywhere he wanted because of his quickness, strength, and handle. Nicknamed “The Answer,” Iverson left Georgetown University following his sophomore season to pursue his NBA dream and showcase his killer crossover. He left an indelible mark on the Philadelphia 76ers in 2001 when he was named regular season MVP and led the franchise to the NBA Finals. In 17 seasons of professional basketball, A.I. was selected to eleven NBA All-Star rosters, scored more than 24,000 points, dished more than 5,000 assists, and was named an All-NBA performer seven times. He won the regular season scoring title four times (1999, 2001, 2002, 2005). Iverson brought a new sense of style to the NBA with his hip-hop influenced fashion. He was the type of player who was never afraid to be himself both on and off the court. Love him or hate him, it was hard not to respect him."},
                    {"title":"Tiger Woods","link":"https://www.youtube.com/embed/e4w3vuA4gCw?autoplay=1&mute=1","text":""},
                    {"title":"Tracy McGrady","link":"https://www.youtube.com/embed/ReKWdgAROLw?autoplay=1&mute=1","text":""},
                    {"title":"Kerry Wood","link":"https://www.youtube.com/embed/Pulci_SBVHk?autoplay=1&mute=1","text":""}];
</script>






<div id="main_container">
    {#each links as link}
        <div class="highlight_container">
            <iframe aspect-ratio='1/1' src={link['link']} title="{link['title']}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            <p>{link['title']}</p>
        </div>
    {/each}
</div>





<style>
    #main_container {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items:center;
        justify-content: space-around;
    }

    .highlight_container{
        /* flex-shrink: 1; */
        flex-grow: 1;
        max-width: 750px;
    }
    iframe {
        width: 95%;
        /* border-radius: 10px; */
    }
       
</style>