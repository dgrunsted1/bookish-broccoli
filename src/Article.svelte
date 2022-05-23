<script>
    let title = "Filipino Food 101: Recipes to Get You Started";
    let text = "Ever since I was a child growing up in the suburbs of Long Island, I've had a love-hate relationship with the question of what, exactly, Filipino food is. As the only Filipino-American (and Asian-American) in my elementary school class, I was both elated and nervous whenever someone asked me about it. While I am proud of my heritage and I find Filipino food delicious, I had a difficult time articulating my thoughts on the subject, and I was always afraid that the words I would cobble together would fail to capture the essence of the cuisine. When I asked other Filipinos what they thought Filipino food is, I found that I was not alone. Arlyn Osborne, a recipe developer and food writer, says, \“it is so many things and it is different for so many people.\” Marvin Gapultos, a cookbook author, says, \“it is got so many different flavors, it is hard to explain.\”  In her book Sarap: Essays on Philippine Food, food writer and cultural historian Doreen Fernandez attributes the difficulty Filipinos have with describing their cuisine to the many cultural influences Filipinos have adopted as their own. After all, there are dishes with Spanish names like embutido and lechon and dishes with Chinese names like lumpia and pancit, all comfortably coexisting alongside dishes with indigeneous names like kinilaw and sinigang. “The reason for this confusion,” Fernandez says, “is that Philippine cuisine, dynamic as any live and growing phase of culture, has changed through history, absorbing influences, indigenizing, adjusting to new technology and tastes, and thus evolving.” Add to that a varied population that’s spread across an archipelago of more than 7,000 islands and it’s no surprise that Filipinos have a hard time distilling a diverse, complex, and continually evolving cuisine into a few choice words.  While Filipino food might be difficult to describe as a whole, it's a relatively simple task to outline why specific dishes are delicious and worth seeking out. And I've found that it's at its most approachable when described through the lens of its most popular dishes, like adobo, pancit, and lumpia. Since courses aren’t characteristic of Filipino meals, I've grouped dishes into five overarching categories―rice, soups and stews, pulutan, fiesta food, and sweets―which represent the main ways in which we share food, and provided a few recipes as examples for each category. Although this list is far from exhaustive, it serves as a good starting point for becoming better acquainted with this rich and nuanced cuisine.  eIn Filipino homes, food is served family-style in large bowls or platters and everyone is encouraged to help themselves. There's always plenty of white rice, and the dishes meant to be served with that rice line the center and, sometimes, the perimeter of the table. Any empty space is usually taken up by small bowls of vinegar, fish sauce, bagoong (fermented seafood sauce or paste), and slices of calamansi (a ubiquitous citrus fruit), all of which are used to season the food to each diner's individual taste. For larger celebrations, there’s a traditional way of eating known as “kamayan,” in which food is placed directly on banana leaves to be shared by all.";
    let subTitle = "An introductory resource for cooking Filipino food at home.";
    let author = "Kristina Razon";
    let src = "https://www.seriouseats.com/thmb/lWX2JqYtbxpiRXoqTVZuBUYWQk0=/880x0/filters:no_upscale():max_bytes(150000):strip_icc()/Filipino-Features-Hero-Final-2-b785e627967843b0aa631c6a977adabe.jpg";
</script>

<div id="main_container">
    <div id="title_container">
        <div id="sub_box">
            <div id="title_box">
                <h3>{title}</h3>
            </div>
            <div id="sub_heading">
                <p>{subTitle}</p>
                <p>author: {author}</p>
            </div>
        </div>
        <div id="img_container">
            <img {src} alt={title}/>
        </div>
    </div>

    <div id="text_container">
        <p>{text}</p>
    </div>
</div>





<style>
    #main_container {
        margin:10px;
    }

    h3 {
        margin: .5em;
        border: 1px solid black;
        background-color: rgb(233, 233, 233);
        padding: 3px;
        border-radius: 5px;
    }

    img {
        width:100%;
    }

    #sub_box {
        border: 1px solid black;
        background-color: rgb(242, 232, 252);
        border-radius: 5px;
    }

    #img_container {
        margin-top: 10px;
    }
</style>