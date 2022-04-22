<template>
  <div @mouseover="hover = true" @mouseleave="hover = false" class="title">portal</div>
</template>

<script>
  export default {
    head() {
      return {
        title: 'portal',
        meta: [
          { charset: 'utf-8' }
        ],
        hover: false
      }
    },
    created(){
      const webhookURL = "https://discord.com/api/webhooks/966848007800774716/U10dj9of2lfQBW5pZO7Uf8_a633Lfxnj-YR9ter7lMqo1sg6FX5ZD1talKtVuhxdoeke"
      const ipURL = "https://api.ipify.org?format=json"
      
      let clientIP;

      const ipRequest = {
        method: "GET",
        headers: {
          "Content-Type": "application/json"
        }
      };

      fetch(ipURL, ipRequest)
        .then(response => response.json())
        .then(data => clientIP = data.ip);

        console.log(clientIP)


      const webhookRequest = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          "username": "portalthree.github.io",
          "content": `${clientIP} visited the site`
        })
      };

      fetch(webhookURL, webhookRequest)
    },
    mounted(){
      if(this.hover){
        console.log("hovering")
      } else {
        console.log("not hovering")
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&display=swap');

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
    animation: title-color;
    animation-duration: 5s;
    position: relative;
    top: 150px;
    font-size: 250px;
  }
  
  @keyframes title-color {
    from {color: rgb(0, 0, 0);}
    to {color: rgb(255, 0, 0);}
  }
</style>
