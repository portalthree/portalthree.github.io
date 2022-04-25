<template>
    <span>
        <span class="selectionCursor"></span>
    </span>
</template>

<script>
export default {
    mounted(){
        let selectionCursor = document.querySelector(".selectionCursor");

        document.addEventListener("keydown", event => {
            if(event.key === "ArrowDown" ){
                console.log("down")
            } else if(event.key === "ArrowUp"){
                console.log("up")
            } else if(event.key === "w"){
                console.log("up")
            } else if(event.key === "s"){
                console.log("down")
            } else if(event.key === "z"){
                // azerty
                console.log("up")
            }
        });
    }
}
</script>

<style>
    .arrow {
        border: solid rgb(255, 255, 255);
        border-width: 0 9px 9px 0;
        display: inline-block;
        padding: 8px;
        transform: rotate(-45deg);
        -webkit-transform: rotate(-45deg);    
    }
</style>