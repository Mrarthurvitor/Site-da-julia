<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Paraaaabeeeenssss JULIAAAAAAA</title>

    <style>
        body {
            background-color: red;
        }

        .painel {
            margin: auto;
            background-color: white;
            width: 500px;
            height: 500px;
            border-radius: 20px;
            text-align: center;
            padding-top: 50px;
            font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        }
        #sim {
            height: 40px;
            width: 60px;
            background-color: red;
            border: 2px solid white;
            border-radius: 10px;
            color: white;
            margin-left: -50px;
            cursor: pointer;
        }
        #nao {
            position: absolute;
            height: 40px;
            width: 60px;
            background-color: red;
            border: 2px solid white;
            border-radius: 10px;
            color: white;
            margin-left: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <div class="painel">
        <h1>Parabéns Júlia 🎉</h1>

        <img src="https://media.tenor.com/124xNuBcUCEAAAAj/kulka.gif" alt="Ursinho fofo apaixonado">

        <h2>Você é incrível né?? 💖</h2>

        <!-- Link agora com aspas (corrigido) -->
        <a href="https://drive.google.com/drive/folders/1eg2xGV-_h4ak2CgVtUU_OGmoBW218WV9?usp=sharing" target="_blank">
            <button id="sim">Sim!</button>
        </a>
        <button onmouseover="fuja()" id="nao">Não!</button>
    </div>

    <script>
        function fuja() {
            var botaoNao = document.getElementById("nao");

            var larguraJanela = window.innerWidth;
            var alturaJanela = window.innerHeight;

            var maxX = larguraJanela - botaoNao.offsetWidth;
            var maxY = alturaJanela - botaoNao.offsetHeight;

            var aleatorioX = Math.floor(Math.random() * maxX);
            var aleatorioY = Math.floor(Math.random() * maxY);

            botaoNao.style.left = aleatorioX + "px";
            botaoNao.style.top = aleatorioY + "px";
        }
    </script>

</body>
</html>
