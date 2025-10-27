<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Paraaaabeeeenssss JULIAAAAAAA</title>

    <style>
        /* === FUNDO ANIMADO === */
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
            background: linear-gradient(-45deg, #ff0000, #ff6b6b, #ffcc70, #ff0000);
            background-size: 400% 400%;
            animation: gradient 10s ease infinite;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* === PAINEL PRINCIPAL === */
        .painel {
            background-color: white;
            width: 90%;
            max-width: 500px;
            height: auto;
            min-height: 450px;
            border-radius: 20px;
            text-align: center;
            padding: 30px 20px 50px;
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.4);
            animation: aparecer 1.5s ease forwards;
            position: relative;
        }

        @keyframes aparecer {
            from { transform: scale(0.7); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        h1 {
            animation: pulseText 2s infinite alternate;
            color: #ff0000;
            font-size: clamp(1.5rem, 5vw, 2.2rem);
        }

        @keyframes pulseText {
            from { text-shadow: 0 0 5px #ff0000; }
            to { text-shadow: 0 0 20px #ff0077; }
        }

        img {
            width: 60%;
            max-width: 200px;
            margin-top: 20px;
            animation: flutuar 3s ease-in-out infinite;
        }

        @keyframes flutuar {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* === BOTÕES === */
        #sim, #nao {
            height: 45px;
            width: 90px;
            border: none;
            border-radius: 10px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.6);
        }

        #sim {
            background-color: red;
            margin-right: 10px;
            animation: brilho 1.5s infinite alternate;
        }

        #nao {
            position: absolute;
            background-color: red;
        }

        @keyframes brilho {
            from { box-shadow: 0 0 10px #ff0000; }
            to { box-shadow: 0 0 25px #ff66b2; }
        }

        #sim:hover {
            transform: scale(1.1);
            background-color: #ff4d4d;
        }

        #nao:hover {
            transform: scale(1.1);
            background-color: #ff4d4d;
        }

        h2 {
            color: #ff0066;
            font-size: clamp(1.1rem, 4vw, 1.5rem);
            margin: 20px 0 30px;
            animation: aparecerTexto 2s ease;
        }

        @keyframes aparecerTexto {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* === AJUSTES RESPONSIVOS === */
        @media (max-width: 600px) {
            .painel {
                padding: 20px;
                height: auto;
            }
            #sim, #nao {
                width: 80px;
                height: 40px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>

    <div class="painel">
        <h1>Parabéns Júlia 🎉</h1>

        <img src="https://media.tenor.com/124xNuBcUCEAAAAj/kulka.gif" alt="Ursinho fofo apaixonado">

        <h2>Você é incrível né?? 💖</h2>

        <a href="https://drive.google.com/drive/folders/1eg2xGV-_h4ak2CgVtUU_OGmoBW218WV9?usp=sharing" target="_blank">
            <button id="sim">Sim!</button>
        </a>
        <button onmouseover="fuja()" id="nao">Não!</button>
    </div>

    <script>
        function fuja() {
            const botaoNao = document.getElementById("nao");
            const painel = document.querySelector(".painel");

            const painelRect = painel.getBoundingClientRect();
            const maxX = painelRect.width - botaoNao.offsetWidth - 20;
            const maxY = painelRect.height - botaoNao.offsetHeight - 20;

            // posição aleatória dentro dos limites do painel
            const aleatorioX = Math.floor(Math.random() * maxX);
            const aleatorioY = Math.floor(Math.random() * maxY);

            botaoNao.style.left = aleatorioX + "px";
            botaoNao.style.top = aleatorioY + "px";
        }

        // Efeito de confete ao clicar em "Sim!"
        const botaoSim = document.getElementById("sim");
        botaoSim.addEventListener("click", () => {
            for (let i = 0; i < 100; i++) {
                const confete = document.createElement("div");
                confete.style.position = "fixed";
                confete.style.width = "8px";
                confete.style.height = "8px";
                confete.style.borderRadius = "50%";
                confete.style.background = `hsl(${Math.random() * 360}, 100%, 60%)`;
                confete.style.top = "50%";
                confete.style.left = "50%";
                confete.style.opacity = "0.8";
                confete.style.transition = "transform 2s ease, opacity 2s ease";
                document.body.appendChild(confete);

                setTimeout(() => {
                    confete.style.transform = `translate(${(Math.random() - 0.5) * 600}px, ${(Math.random() - 0.5) * 800}px) rotate(${Math.random() * 720}deg)`;
                    confete.style.opacity = "0";
                }, 50);

                setTimeout(() => confete.remove(), 2000);
            }
        });

        // Centraliza novamente o botão "Não" no início
        window.onload = () => {
            const botaoNao = document.getElementById("nao");
            botaoNao.style.left = "55%";
            botaoNao.style.top = "75%";
        };
    </script>

</body>
</html>
