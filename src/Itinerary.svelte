<script>

let entry_types = ['activity', 'travel', 'stay', 'pass'];
let entries = [];

const add_entry = (e) => {
    var vals = document.getElementsByTagName('input');
    let result = [];
    [...vals].forEach(element => {
                result[element.name] = element.value;
            });
}
</script>

<div id="main_container">
    {#each entries as curr}
    <div class="entry_container">
        {#each curr as [key, val]}
            <div>
                <div>
                    {key}: 
                </div>
                <div>
                    {val}
                </div>
            </div>
        {/each}
    </div>
        
    {/each}

    <div id="new_entry_container">
        <div class="row"><label for="title">Title</label><input type="text" name="title"></div>
        <div class="row"><label for="desc">Description</label><input type="text" name="desc"></div>
        <div class="row"><label for="start">Start</label><input type="date" name="start"></div>
        <div class="row"><label for="end">End</label><input type="date" name="end"></div>
        <div class="row"><label for="location">Location</label><input type="text" name="location"></div>
        <div class="row"><label for="cost">Cost</label><input type="number" name="cost"></div>
        <div class="row"><label for="type">Type</label><select type="dropdown" name="Type">
            {#each entry_types as curr}
                <option value={curr}>{curr}</option>
            {/each}
        </select></div>
        <div class="button" id="add_entry" on:click={add_entry}>add</div>
    </div>
</div>




<style>
.row {
    display: flex;
    flex-direction: row;
}
.button {
    background: red;
}
</style>