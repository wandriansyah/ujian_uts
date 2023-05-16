<template>

  <html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>Alquran Indonesia - By Wandriansyah</title>

  
  </head>
  <body>
    
    <div class="container">

      <div class="row">

        <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
          
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
            <div class="navbar-nav">
              <a class="nav-link active" href="/">Home <span class="sr-only"></span></a>
              <a class="nav-link" href="/quran">Alquran</a>
            </div>
          </div>
        </nav>

      </div>

    </div>


    <div class="container">

        <div class="row" v-for="item in list" :key="item">

          <div class="card" >
              <div class="card-body">
                <h5 class="card-title">{{item.nomor}}</h5>
                <p class="card-text">{{item.nama}}</p>
                <p class="card-text">{{item.deskripsi}}</p>
              </div>
          </div>

      </div>

    </div>

  </body>
</html>

</template>

<script>

import axios from "axios";

export default {
    
    name: "App",

    data(){

      return{

        list: [],

      };

    },

    async mounted()
    {
    let result = await axios.get("https://api.equran.id/api/v2/surat");

    console.warn("Api data", result.data.data);
    this.list = result.data.data;
    },

};

</script>


