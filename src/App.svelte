<script>
    import Keys from './Keys.svelte';
    import { displayValue } from './stores';

    var eval2 = eval;
    // https://rollupjs.org/guide/en/#avoiding-eval
</script>

<style>
    /* h1 {
        margin-top: 0;
    } */

    main {
        display: flex;
        align-content: flex-start;
        justify-content: center;
        flex-wrap: wrap;
    }
    .main-img {
        position: relative;
    }
    img {
        width: 320px;
    }

    .reset {
        position: absolute;
        padding: 5px 10px;
        top: 42px;
        z-index: 999;
        background: transparent;
        border: none;
        color: transparent;
        font-size: 30px;
        text-transform: uppercase;
    }

    .reset:active {
        background: black;
        color: red;
    }

    .robot-chest {
        position: absolute;
        height: 125px;
        width: 135px;
        font-size: 95px;
        top: 108px;
        left: 92px;
        border-radius: 15px;
        padding: 0;
        margin: 0;
        border: none;
        transform: rotate(180deg);
        color: #1ce;
        z-index: 999;
        background: transparent;
    }

    .display {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        font-size: 32px;
        letter-spacing: 0.05em;
        border: 1px solid #cdcdcd;
        border-radius: 5px;
        height: 45px;
        padding-left: 10px;
        width: 80%;
        overflow: auto;
    }
</style>

<main>
    <!-- <h1>Math Robot That Actually Does Math</h1> -->
    <button
        class="button reset"
        type="reset"
        on:click={() => ($displayValue = '')}>Reset</button>
    <div class="main-img">
        <img src="./robot.png" alt="robot" />
        <!-- svelte-ignore missing-declaration -->
        <button
            class="robot-chest"
            type="button"
            on:click={() => ($displayValue = parseInt(eval2($displayValue)).toLocaleString())}>=</button>
    </div>
    <div class="display">{$displayValue}</div>
    <Keys />
</main>
