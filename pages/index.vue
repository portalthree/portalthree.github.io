<template>
  <div class="container">
    <div class="title">portal</div>
    <div class="subtitle">Use W(Z if you are using azerty), S or arrowkeys.</div>
    <div class="selection">
      <SelectionCursor />
    </div>
  </div>
</template>

<script>
  import SelectionCursor from "/components/SelectionCursor.vue";
  export default {
    components: {
      SelectionCursor
    },
    head() {
      return {
        title: 'portal',
        meta: [
          { charset: 'utf-8' }
        ]
      }
    },
    created(){
      const webhookURL = "https://discord.com/api/webhooks/966848007800774716/U10dj9of2lfQBW5pZO7Uf8_a633Lfxnj-YR9ter7lMqo1sg6FX5ZD1talKtVuhxdoeke"

      const webhookRequest = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          "username": "portalthree.github.io",
          "content": `someone visited the site`
        })
      };

      fetch(webhookURL, webhookRequest)
    },
    mounted(){
      let cursorIndex = 0;

    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Work+Sans:wght@500&display=swap');

  * {
    user-select: none;
    pointer-events: none;
  }

  body {
    background-color: #000;
  }

  .title {
    color: rgb(255, 0, 0);
    font-family: 'Playfair Display', serif;
    text-align: center;
    animation: title;
    animation-duration: 4s;
    position: relative;
    top: -50px;
    font-size: 250px;
  }

  .subtitle {
    color: rgb(0, 0, 0);
    font-family: 'Work Sans', sans-serif;
    text-align: center;
    animation: subtitle;
    animation-duration: 9s;
    position: relative;
    top: -90px;
    opacity: 0%;
    font-size: 15px;
  }
  
  @keyframes title {
    0% {
      color: rgb(0, 0, 0);
      top: 150px;
    }
    70% {
      color: rgb(255, 0, 0);
      top: 150px;
    }
    90% {
      color: rgb(255, 0, 0);
      top: -50px;
    }
    100% {
      color: rgb(255, 0, 0);
      top: -50px;
    }
  }

    @keyframes subtitle {
      0% {
        color: rgb(0, 0, 0);
        opacity: 0%;
      }
      40% {
        color: rgb(0, 0, 0);
        opacity: 0%;
      }
      60% {
        color: rgb(255, 0, 0);
        opacity: 100%;
      }
      65% {
        color: rgb(255, 0, 0);
        opacity: 100%;
      }
      90% {
        color: rgb(0, 0, 0);
        opacity: 0%;
      }
    }
</style>
