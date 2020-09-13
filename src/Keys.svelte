<script>
	import {displayValue} from './stores'

    const keys = [...Array.from(Array(10).keys()), '+', '-'];
</script>

<style>
.keys-wrapper {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: flex-start;


}

button {
    margin: 5px 10px;
    padding: 15px 25px;
    background: #ff3e00;
    color: white;
}

button:active {
    background: salmon;
}
</style>

<div class='keys-wrapper'>
{#each keys as key}
    <button class="button" value="{key}" on:click={()=> $displayValue = `${$displayValue}${key}`}>{key}</button>
{/each}
</div>
