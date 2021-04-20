<script>
    export let price;
    export let stocked;
    export let name;
</script>

<style>
    .green-button {
    background-color: #4CAF50;
    border: none;
    color: white;
    padding: 8px 16px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 12px;
    margin: 4px 2px;
    transition-duration: 0.4s;
    cursor: pointer;
    }

    .disabled-button {
    background-color: #A9A9A9;
    border: none;
    color: #DCDCDC;
    padding: 8px 16px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 12px;
    margin: 4px 2px;
    transition-duration: 0.4s;
    }  
</style>

<tr>
    <td>{name}</td>
    <td>{price}</td>
    {#if stocked}
    <button class="green-button">Add</button>
    {:else}
    <button class="disabled-button">Add</button>
    {/if}
</tr>