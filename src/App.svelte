<!-- Script JS -->
<script>
    import * as d3 from "d3"

    function max(array){
        var maxValue = 0
        for (let i = 1; i < array.length; i++) {
            if (array[i] > maxValue) {
                maxValue = array[i];
            }
        }
        return maxValue
    }

    let nums_1 = [21, 33, 42, 54, 63, 71, 77, 87, 92, 98]
    let nums_2 = [23, 35, 45, 56, 50, 43, 38, 32, 28, 25]
    let anios = [2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023]
    
    let maximo_1 = max(nums_1);
    let maximo_2 = max(nums_2);
    let maximo = d3.max([maximo_1, maximo_2]);
    
    let color_1 = d3
    .scaleLinear()
    .domain([0, d3.max(nums_1)])
    .range(["#D7FFDE", "#76D287"])

    let color_2 = d3
    .scaleLinear()
    .domain([0, d3.max(nums_1)])
    .range(["#E4CDFF", "#7F42C8"])

    let color_1_1 = d3
    .scaleLinear()
    .domain([0, d3.max(nums_1)])
    .range(["#E3E9F4", "#003FBD"])

    let color_1_2 = d3
    .scaleLinear()
    .domain([50, d3.max(nums_1)])
    .range(["#4A81EF", "#00BD6B"])


    let color_2_1 = d3
    .scaleLinear()
    .domain([0, d3.max(nums_1)])
    .range(["#E3E9F4", "#003FBD"])

    let color_2_2 = d3
    .scaleLinear()
    .domain([0, d3.max(nums_2)])
    .range(["#FD0000", "#5489F1"])

    let ancho = d3
    .scaleLinear()
    .domain([0, maximo])
    .range([0, 570])

</script>

<!-- Estructura contenido HTML -->
<div class="header">
    <h1>Microstuff vs Pear</h1>
    <h2 style = "text-align:center; margin-bottom: 20px; color: white; width: 600px">Ventas de licencias de software en millones de U$D en   la última década</h2>
</div>

<div class = "logos">
    <div class = "logo">
        <img id="micro" src="./images/microstuffmonochrom.png" alt="">
    </div>
    <div class = "logo">
        <img id="pear" src="./images/pearlogomonochrom.png" alt="">
    </div>
</div>

<h1 style = "font-size: 25px; color: #6D6D6D">Ventas en $MM</h1>

<div class = "container" style="width: 1250px">
    <div class="container_chart_1" style="width: 600px">
        {#each nums_1 as num, index}
            <div class="mag">
                <h3 style = "font-size: {20}px; margin-bottom: 10px">{num}</h3>
                <div class="barra_l" style="width: {ancho(num)}px; background:{color_1(num)}"></div>
            </div>
        {/each}
    </div>

    <div class="container_chart_anio">
        {#each anios as num}
            {#if num == 2018}
                <div class="anio_dist">
                    <h3 style = "font-size: {14}px; text-align:center; color: white; font-weight: bold">{num}</h3>
                    <div class="info">
                        <h3 style = "font-size: {15}px; text-align:center; color: white; font-weight: regular">
                            Microstuff muta su modelo de ventas a uno de suscripción mensual
                        </h3>
                    </div>
                </div>
            {/if}
            {#if num != 2018}
                <div class="anio">
                    <h3 style = "font-size: {14}px; text-align:center; color: white; font-weight: bold">{num}</h3>
                </div>
            {/if}
        {/each}
    </div>

    <div class="container_chart_2" style="width: 600px">
        {#each nums_2 as num, index}
            <div class="mag">
                <div class="barra_r" style="width: {ancho(num)}px; background:{color_2(num)}"></div>
                <h3 style = "font-size: {20}px; margin-bottom: 10px">{num}</h3>
            </div>
        {/each}
    </div>
</div>

<div class="flourish_container">
    <div class="flourish-embed flourish-chart" style="width: 42.5%; margin-right: 20px; margin-top: 15px; margin-bottom: 30px" data-src="visualisation/19450884"><script src="https://public.flourish.studio/resources/embed.js"></script>
        <h1 style = "font-size: 25px; color: #6D6D6D">Market share</h1>
        <noscript>
            <img src="https://public.flourish.studio/visualisation/19450884/thumbnail" width="100%" alt="chart visualization" />
        </noscript>
    </div>
    <div class="flourish-embed flourish-bar-chart-race" style="width: 42.5%; margin-right: 20px; margin-top: 15px; margin-bottom: 30px" data-src="visualisation/19450880"><script src="https://public.flourish.studio/resources/embed.js"></script>
        <h1 style = "font-size: 25px; color: #6D6D6D">La carrera por el mercado ($MM)</h1>
        <noscript>
            <img src="https://public.flourish.studio/visualisation/19450880/thumbnail" width="100%" alt="bar-chart-race visualization" />
        </noscript>
    </div>
</div>
<div class="footer">
    <img src="./images/ditella.png" alt="">
    <h2 style = "text-align:center; margin-top: 20px; margin-bottom: 20px; color: white; font-size:20px">Desarrollado por Dafydd Jenkins</h2>
    <div class="socials">
        <a href="https://github.com/Dafydd8">
            <img src="./images/GitHub.png" alt="">
        </a>
        <a href="https://www.instagram.com/dafydd.jenkins_?igsh=YnYxbzM4cjF6NzIx&utm_source=qr">
            <img src="./images/Instagram.png" alt="">
        </a>
        <a href="https://t.me/daj088">
            <img src="./images/Telegram.png" alt="">
        </a>
    </div>
    
</div>


<!-- Estilos CSS -->
<style>
    @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@100..900&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,200..1000;1,200..1000&display=swap');

    .header {
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: #5a84e0;
    }

    .footer {
        background-color: #5a84e0;
        display: flex;
        justify-content: space-around;
        align-items: center;
        gap: 30px;
    }

    .socials {
        display: flex;
        justify-content: center;
        gap: 5px;
    }


    .flourish_container {
        display: flex;
        justify-content: center;
        margin-top: 50px;
        margin-top: 3%;
        background-color: #ffffff;
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
    }

    .barra_l {
        height: 20px;
        background-color: grey;
        margin-bottom: 20px;
        margin-top: 10px;
        margin-right: -10px;
        border-top-left-radius: 15px;
        border-bottom-left-radius: 15px;
    }
    .barra_r {
        height: 20px;
        background-color: grey;
        margin-bottom: 20px;
        margin-top: 10px;
        margin-left: -10px;
        border-top-right-radius: 15px;
        border-bottom-right-radius: 15px;
    }
    .container_chart_2 {
        margin-left: auto;
        margin-right: auto;
        z-index: 0;
        width: 600px;
    }

    .logos {
        display: flex;
        margin-left: auto;
        margin-right: auto;
        margin-top: 40px;
        margin-bottom: 15px;
    }
    .logo {
        display: flex;
        margin-left: auto;
        margin-right: auto;
    }

    .container_chart_anio {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-left: auto;
        margin-right: auto;
        z-index: 1;
    }

    .container_chart_1 {
        display: flex;
        flex-direction: column;
        align-items: end;
        margin-left: auto;
        margin-right: auto;
    }

    .container {
        display: flex;
        margin-left: auto;
        margin-right: auto;
    }

    .mag {
        display: flex;
        gap: 10px; /* Espacio entre imagen y texto */
        margin: 0px;
        display: flex;
        align-items: center;
    }
    .anio {
        background-color: #7598e2;
        display: flex; /* Espacio entre imagen y texto */
        height: 40px;
        width: 40px;
        align-items: center;
        margin-bottom: 10px;
        border-radius: 100%;
        justify-content: center;
    }
    .anio_dist {
        position: relative;
        background-color: #2f00ff;
        display: flex; /* Espacio entre imagen y texto */
        height: 40px;
        width: 40px;
        align-items: center;
        margin-bottom: 10px;
        border-radius: 100%;
        justify-content: center;
    }
    .anio_dist::after {
      content: "*";  /* El asterisco */
      color: red;  /* Color del asterisco */
      font-size: 25px;  /* Tamaño del asterisco */
      position: absolute;
      top: -10px;
      right: -2px;
      font-weight: bold;
    }

    h1 {
        font-optical-sizing: auto;
        font-style: normal;
        margin-top: 30px;
        font-family: "Outfit", system-ui;
        font-weight:600;
        text-align:center;
        margin-bottom: 20px;
        color: white;
        font-size: 50px;
    }

    h2 {
        margin-bottom: 10px;
        font-size: 25px;
        font-family: "Nunito", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
    }

    h3 {
        margin: 0px;
        font-family: "Nunito", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 10px;
    }

    .info {
      visibility: hidden;
      width: 150px;
      background-color: #2f00ff;
      color: #fff;
      text-align: center;
      border-radius: 5px;
      padding: 10px;
      position: absolute;
      top: -90%;  /* Posición debajo del div */
      left: -200%;
      transform: translateX(-50%);
      z-index: 1;
    }

    .anio_dist:hover .info {
      visibility: visible;
    }
</style>
