<script>

let entry_types = ['activity', 'travel', 'stay'];
let entries = [];
let curr_type = entry_types[0];
let input_data = [{"activity": 
                    [[{"name": "Title", "type": "text"}, {"name": "description", "type": "text"}], [{"name": "start", "type": "date"}, {"name": "end", "type": "date"}, {"name": "location", "type": "text"}, {"name": "link", "type": "text"}]]
                }, {"travel": [
                    [[{"name": "Title", "type": "text"}, {"name": "description", "type": "text"}], [{"name": "start", "type": "date"}, {"name": "end", "type": "date"}, {"name": "departure location", "type": "text"}, {"name": "arrival location", "type": "text"}, {"name": "link", "type": "text"}]]
                ]}, {"stay": [
                    [[{"name": "Title", "type": "text"}, {"name": "description", "type": "text"}], [{"name": "start", "type": "date"}, {"name": "end", "type": "date"}, {"name": "location", "type": "text"}, {"name": "link", "type": "text"}]]
                ]}];

const add_entry = (e) => {
    let vals = document.getElementsByTagName('input');
    let result = {};
    [...vals].forEach(element => {
        result[element.name] = element.value;
        element.value = "";
    });
    entries.push(result);
    entries = entries;
    
}
</script>

<div id="main_container">
    {#each entries as curr}
    <div class="entry_container">
        {#each Object.entries(curr) as [key, val]}
            <div class="row">
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
        <div class="input"><label for="type">Type</label><select type="dropdown" name="Type" bind:value={curr_type}>
            {#each entry_types as curr}
                <option value={curr}>{curr}</option>
            {/each}</select></div>
        {#each input_data[curr_type] as rows}
        <div class="row">
            {#each rows as curr}
                <div class="input"><label for={curr.name}>{curr.name}</label><input type="text" name={curr.name}></div>
            {/each}
        </div>
        {/each}




        
        <button class="button" on:click={add_entry}>ADD</button>
    </div>
</div>




<style>

#main_container {
    display: flex;
    flex-direction: column;
}
.row {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin: 10px;
    flex-wrap: wrap;
}

.entry_container {
    display: flex;
    flex-direction: column;
}

#new_entry_container {
    /* max-width: 600px; */
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.row > div, label, input {
    margin: 10px;
}

/* .row > input {
flex-grow: 5;
flex-shrink: 0;

} */

.button {
  background-color: #c2fbd7;
  border-radius: 100px;
  box-shadow: rgba(44, 187, 99, .2) 0 -25px 18px -14px inset,rgba(44, 187, 99, .15) 0 1px 2px,rgba(44, 187, 99, .15) 0 2px 4px,rgba(44, 187, 99, .15) 0 4px 8px,rgba(44, 187, 99, .15) 0 8px 16px,rgba(44, 187, 99, .15) 0 16px 32px;
  color: green;
  padding: 7px 20px;
  text-align: center;
  transition: all 250ms;
}

.input {
    display: flex;
    flex-direction: row;
}

.button:hover {
  box-shadow: rgba(44,187,99,.35) 0 -25px 18px -14px inset,rgba(44,187,99,.25) 0 1px 2px,rgba(44,187,99,.25) 0 2px 4px,rgba(44,187,99,.25) 0 4px 8px,rgba(44,187,99,.25) 0 8px 16px,rgba(44,187,99,.25) 0 16px 32px;
  transform: scale(1.05) rotate(-1deg);
}

@media only screen and (min-width: 600px) {
    .row, .entry_container, #new_entry_container {
        flex-direction: row;
    }

    .row {
        flex-wrap: nowrap;
    }
}
</style>