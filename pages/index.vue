<template>
  <div class="title">portal</div>
</template>

<script>
  export default {
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
        .then(data => console.log(data));


      const webhookRequest = {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          "username": "portalthree.github.io",
          "content": "``` ```someone visited the website.\n__**TODO**:__ add ip adress *(why is it blocked by the browser?)*"
        })
      };

      fetch(webhookURL, webhookRequest)
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&display=swap');

  * {
    user-select: none;
    pointer-events: none;
  }

  .title {
    font-family: 'Playfair Display', serif;
    font-size: 250px;
    text-align: center;
    margin-top: 10%;
  }
</style>
