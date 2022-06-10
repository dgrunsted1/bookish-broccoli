<script>

let entry_types = ['activity', 'travel', 'stay', 'pass'];
let entries = [];

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
    flex-direction: row;
}

.row > div, label, input {
    margin: 10px;
}

.button {
  background-color: #c2fbd7;
  border-radius: 100px;
  box-shadow: rgba(44, 187, 99, .2) 0 -25px 18px -14px inset,rgba(44, 187, 99, .15) 0 1px 2px,rgba(44, 187, 99, .15) 0 2px 4px,rgba(44, 187, 99, .15) 0 4px 8px,rgba(44, 187, 99, .15) 0 8px 16px,rgba(44, 187, 99, .15) 0 16px 32px;
  color: green;
  padding: 7px 20px;
  text-align: center;
  transition: all 250ms;
}

.button:hover {
  box-shadow: rgba(44,187,99,.35) 0 -25px 18px -14px inset,rgba(44,187,99,.25) 0 1px 2px,rgba(44,187,99,.25) 0 2px 4px,rgba(44,187,99,.25) 0 4px 8px,rgba(44,187,99,.25) 0 8px 16px,rgba(44,187,99,.25) 0 16px 32px;
  transform: scale(1.05) rotate(-1deg);
}
</style>