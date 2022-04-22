<template>
  <span>
    <span class="vueCursor"></span>
  </span>
</template>
<script>
export default {
  props: {
    cursorSize: {
      default: 10
    },
    cursorColor: {
      default: "#aaa"
    }
  },

  mounted() {
    let vueCursor = document.querySelector(".vueCursor");

    let cursorX;
    let cursorY;

    let cursorWidth = 20;
    let cursorHeight = 20;

    let cursorColor = this.cursorColor

    let cursorSpeed = 85;

    document.addEventListener("mousemove", event => {
        cursorX = event.clientX;
        cursorY = event.clientY;
        updateCursor();

    });

    document.addEventListener("mousedown", event => {
        cursorX = event.clientX
        cursorY = event.clientY;
        cursorWidth = 18;
        cursorHeight = 18;
        cursorSpeed = 200;
        updateCursor();
    });

    document.addEventListener("mouseup", event => {
        cursorX = event.clientX
        cursorY = event.clientY;
        cursorWidth = 20;
        cursorHeight = 20;
        cursorSpeed = 85;
        updateCursor();
    }); 

    function updateCursor() {
        vueCursor.style.cssText = `
        transform: translate3d(${cursorX}px, ${cursorY}px, 0);
        width: ${cursorWidth}px;
        height: ${cursorHeight}px;
        background-color: ${cursorColor};
        transition: transform ${cursorSpeed}ms ease-out;`;
    }
  },
};

</script>

<style>

    * {
        cursor: none;
    }
    
    .vueCursor {
        position: fixed;
        top: 0;
        left: -0.3%;
        z-index: 100000;
        border-radius: 50%;
        pointer-events: none;
    }

</style>
