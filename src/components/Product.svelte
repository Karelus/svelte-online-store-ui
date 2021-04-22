<script>
    export let price;
    export let stocked;
    export let name;
    export let onAddButtonClick;

    let handleAddButtonClick = () => {
        onAddButtonClick(price);
    };
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
        margin: 4px 8px;
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
        margin: 4px 8px;
        transition-duration: 0.4s;
    }  
</style>

<tr>
    {#if stocked}
        <td>{name}</td>
        <td>{price} €</td>
        <button class="green-button" on:click={handleAddButtonClick}>Add</button>
    {:else}
        <td style="color:red">{name}</td>
        <td>{price} €</td>
        <button class="disabled-button" disabled>Add</button>
    {/if}
</tr>