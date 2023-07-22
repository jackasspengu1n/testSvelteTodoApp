<script>
    export let onClick = () => {};
</script>

<style>
    .circle-button {
        display: inline-block;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        border: 2px solid black;
        cursor: pointer;
        transition: background-color 0.2s ease;
    }

    .circle-button:hover {
        background-color: rgba(128, 128, 128, 0.5);
    }

    .circle-button:active {
        background-color: rgba(64, 64, 64, 0.5);
    }
</style>

<div class="circle-button" on:click={onClick}></div>
