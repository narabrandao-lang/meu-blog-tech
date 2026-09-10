<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Glow Diary ✨</title>

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;600;700&family=Poppins:wght@300;400;500;600&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        :root {
            --rosa: #d86b9d;
            --rosa-claro: #fce8f1;
            --rosa-muito-claro: #fff8fb;
            --roxo: #8d6aa8;
            --texto: #3c3040;
            --branco: #ffffff;
            --borda: #f0d5e1;
            --sombra: 0 15px 40px rgba(151, 82, 119, 0.13);
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: var(--rosa-muito-claro);
            color: var(--texto);
            transition: 0.4s;
        }

        body.dark {
            --rosa-muito-claro: #211a24;
            --branco: #2d2330;
            --texto: #fff0f7;
            --rosa-claro: #382735;
            --borda: #543c50;
            --sombra: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        /* MENU */

        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(255, 248, 251, 0.9);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid var(--borda);
        }

        body.dark header {
            background: rgba(33, 26, 36, 0.9);
        }

        nav {
            max-width: 1150px;
            margin: auto;
            padding: 18px 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 28px;
            font-weight: bold;
            color: var(--rosa);
        }

        .logo span {
            color: var(--roxo);
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 25px;
        }

        nav a {
            text-decoration: none;
            color: var(--texto);
            font-size: 14px;
            transition: 0.3s;
        }

        nav a:hover {
            color: var(--rosa);
        }

        .tema {
            border: none;
            background: var(--rosa-claro);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
        }

        /* HERO */

        .hero {
            max-width: 1150px;
            margin: 70px auto;
            padding: 0 25px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            align-items: center;
            gap: 60px;
        }

        .tag {
            display: inline-block;
            background: var(--rosa-claro);
            color: var(--rosa);
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 12px;
            margin-bottom: 20px;
            letter-spacing: 1px;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(42px, 6vw, 70px);
            line-height: 1.05;
            margin-bottom: 20px;
        }

        .hero h1 span {
            color: var(--rosa);
        }

        .hero p {
            color: #8a7887;
            line-height: 1.8;
            margin-bottom: 30px;
        }

        .botao {
            display: inline-block;
            padding: 14px 25px;
            border-radius: 30px;
            background: linear-gradient(135deg, #d86b9d, #9d78b7);
            color: white;
            text-decoration: none;
            font-size: 14px;
            box-shadow: 0 10px 25px rgba(216, 107, 157, 0.25);
            transition: 0.3s;
        }

        .botao:hover {
            transform: translateY(-4px);
        }

        .hero-card {
            position: relative;
            min-height: 390px;
            border-radius: 35px;
            background:
                radial-gradient(circle at 20% 20%, #ffffff 0 4%, transparent 5%),
                radial-gradient(circle at 80% 30%, #ffffff 0 3%, transparent 4%),
                linear-gradient(145deg, #f7c7da, #d9c5e9);
            box-shadow: var(--sombra);
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-card::before {
            content: "✦";
            position: absolute;
            top: 35px;
            left: 45px;
            font-size: 35px;
            color: white;
        }

        .hero-card::after {
            content: "♡";
            position: absolute;
            bottom: 35px;
            right: 45px;
            font-size: 55px;
            color: white;
        }

        .flor {
            font-size: 150px;
            filter: drop-shadow(0 15px 15px rgba(0,0,0,0.08));
            animation: flutuar 4s ease-in-out infinite;
        }

        @keyframes flutuar {
            0%, 100% {
                transform: translateY(0) rotate(-3deg);
            }

            50% {
                transform: translateY(-15px) rotate(3deg);
            }
        }

        /* SEÇÃO */

        section {
            max-width: 1150px;
            margin: 100px auto;
            padding: 0 25px;
        }

        .titulo {
            text-align: center;
            margin-bottom: 45px;
        }

        .titulo small {
            color: var(--rosa);
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 11px;
        }

        .titulo h2 {
            font-family: 'Playfair Display', serif;
            font-size: 42px;
            margin-top: 8px;
        }

        /* POST */

        .post {
            background: var(--branco);
            border: 1px solid var(--borda);
            border-radius: 28px;
            padding: 35px;
            box-shadow: var(--sombra);
        }

        .post-topo {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .categoria {
            color: var(--rosa);
            font-size: 12px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .data {
            font-size: 12px;
            color: #9a8996;
        }

        .post h3 {
            font-family: 'Playfair Display', serif;
            font-size: 34px;
            margin-bottom: 15px;
        }

        .post p {
            color: #8a7887;
            line-height: 1.8;
        }

        .post-imagem {
            height: 250px;
            margin: 25px 0;
            border-radius: 20px;
            background:
                radial-gradient(circle at 30% 30%, #ffffff 0 3%, transparent 4%),
                radial-gradient(circle at 70% 60%, #ffffff 0 4%, transparent 5%),
                linear-gradient(135deg, #e8a9c5, #cdb7df);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
        }

        .ler {
            display: inline-block;
            margin-top: 25px;
            color: var(--rosa);
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
        }

        /* CARDS */

        .cards {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .card {
            background: var(--branco);
            border: 1px solid var(--borda);
            padding: 30px;
            border-radius: 25px;
            box-shadow: var(--sombra);
            transition: 0.3s;
        }

        .card:hover {
            transform: translateY(-8px);
        }

        .icone {
            width: 55px;
            height: 55px;
            border-radius: 18px;
            background: var(--rosa-claro);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 25px;
            margin-bottom: 20px;
        }

        .card h3 {
            font-family: 'Playfair Display', serif;
            font-size: 24px;
            margin-bottom: 10px;
        }

        .card p {
            color: #8a7887;
            font-size: 14px;
            line-height: 1.7;
        }

        /* SOBRE */

        .sobre {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 45px;
            align-items: center;
            background: var(--branco);
            padding: 45px;
            border-radius: 30px;
            border: 1px solid var(--borda);
            box-shadow: var(--sombra);
        }

        .avatar {
            width: 210px;
            height: 210px;
            border-radius: 50%;
            background: linear-gradient(145deg, #f7c7da, #d9c5e9);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 85px;
        }

        .sobre h2 {
            font-family: 'Playfair Display', serif;
            font-size: 38px;
            margin-bottom: 15px;
        }

        .sobre p {
            color: #8a7887;
            line-height: 1.8;
        }

        /* CONTATO */

        .contato {
            text-align: center;
            background: linear-gradient(135deg, #f9d8e7, #e4d7ef);
            padding: 60px 25px;
            border-radius: 35px;
        }

        .contato h2 {
            font-family: 'Playfair Display', serif;
            font-size: 40px;
            margin-bottom: 12px;
        }

        .contato p {
            color: #765f70;
            margin-bottom: 25px;
        }

        /* FOOTER */

        footer {
            background: #30242f;
            color: white;
            text-align: center;
            padding: 45px 20px;
            margin-top: 100px;
        }

        footer .logo {
            margin-bottom: 10px;
        }

        footer p {
            color: #cbbbc8;
            font-size: 13px;
        }

        .social {
            margin: 20px 0;
            display: flex;
            justify-content: center;
            gap: 12px;
        }

        .social a {
            width: 38px;
            height: 38px;
            border-radius: 50%;
            background: #443444;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: white;
            transition: 0.3s;
        }

        .social a:hover {
            transform: translateY(-4px);
            background: #d86b9d;
        }

        /* RESPONSIVO */

        @media (max-width: 800px) {

            nav ul {
                display: none;
            }

            .hero {
                grid-template-columns: 1fr;
                margin-top: 45px;
            }

            .hero-card {
                min-height: 300px;
            }

            .cards {
                grid-template-columns: 1fr;
            }

            .sobre {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .avatar {
                margin: auto;
            }

            .post {
                padding: 25px;
            }

            section {
                margin: 70px auto;
            }
        }
    </style>
</head>

<body>

    <!-- MENU -->

    <header>
        <nav>
            <div class="logo">
                Glow<span>Diary</span> ✦
            </div>

            <ul>
                <li><a href="#inicio">Início</a></li>
                <li><a href="#posts">Posts</a></li>
                <li><a href="#categorias">Categorias</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>

            <button class="tema" onclick="mudarTema()">🌙</button>
        </nav>
    </header>

    <!-- INÍCIO -->

    <main id="inicio">

        <div class="hero">

            <div>
                <span class="tag">✦ Bem-vinda ao meu universo</span>

                <h1>
                    Pequenos detalhes,
                    <span>grandes inspirações.</span>
                </h1>

                <p>
                    Um cantinho para compartilhar ideias, criatividade,
                    tecnologia, beleza e tudo aquilo que deixa a vida
                    ainda mais especial.
                </p>

                <a href="#posts" class="botao">
                    Explorar o blog ✨
                </a>
            </div>

            <div class="hero-card">
                <div class="flor">🌷</div>
            </div>

        </div>

        <!-- POST -->

        <section id="posts">

            <div class="titulo">
                <small>Meu diário digital</small>
                <h2>Post em destaque</h2>
            </div>

            <article class="post">

                <div class="post-topo">
                    <span class="categoria">Tecnologia</span>
                    <span class="data">10 Setembro, 2026</span>
                </div>

                <h3>
                    Criatividade e tecnologia: uma combinação incrível
                </h3>

                <p>
                    A tecnologia faz parte da nossa rotina e também pode
                    ser uma ferramenta poderosa para transformar ideias
                    em projetos incríveis.
                </p>

                <div class="post-imagem">
                    💻 ✨ 🌸
                </div>

                <p>
                    Aprender programação permite criar sites, jogos,
                    aplicativos e muitas outras coisas. O mais importante
                    é começar, testar novas ideias e não ter medo de errar.
                </p>

                <a href="#" class="ler" onclick="mensagem(); return false;">
                    Continuar lendo → 
                </a>

            </article>

        </section>

        <!-- CATEGORIAS -->

        <section id="categorias">

            <div class="titulo">
                <small>Explore</small>
                <h2>Minhas categorias</h2>
            </div>

            <div class="cards">

                <div class="card">
                    <div class="icone">💻</div>
                    <h3>Tecnologia</h3>
                    <p>
                        Programação, sites, aplicativos e novidades
                        do mundo digital.
                    </p>
                </div>

                <div class="card">
                    <div class="icone">🎨</div>
                    <h3>Criatividade</h3>
                    <p>
                        Ideias, design, inspiração e projetos
                        criativos para colocar a imaginação em prática.
                    </p>
                </div>

                <div class="card">
                    <div class="icone">💗</div>
                    <h3>Meu universo</h3>
                    <p>
                        Pensamentos, descobertas, sonhos e pequenas
                        coisas que fazem parte do meu dia.
                    </p>
                </div>

            </div>

        </section>

        <!-- SOBRE -->

        <section id="sobre">

            <div class="sobre">

                <div class="avatar">
                    🌸
                </div>

                <div>
                    <h2>Sobre mim ♡</h2>

                    <p>
                        Oi! Eu sou a pessoa por trás do Glow Diary.
                        Criei este espaço para reunir minhas ideias,
                        aprendizados e projetos.
                    </p>

                    <br>

                    <p>
                        Aqui você vai encontrar um pouco de tecnologia,
                        criatividade e tudo aquilo que me inspira.
                    </p>
                </div>

            </div>

        </section>

        <!-- CONTATO -->

        <section id="contato">

            <div class="contato">

                <h2>Vamos conversar? 💌</h2>

                <p>
                    Gostou do blog? Obrigada por visitar meu cantinho!
                </p>

                <a href="mailto:contato@glowdiary.com" class="botao">
                    Enviar uma mensagem
                </a>

            </div>

        </section>

    </main>

    <!-- RODAPÉ -->

    <footer>

        <div class="logo">
            Glow<span>Diary</span> ✦
        </div>

        <p>
            Um pequeno espaço para grandes ideias.
        </p>

        <div class="social">
            <a href="#">♡</a>
            <a href="#">◎</a>
            <a href="#">✦</a>
        </div>

        <p>
            © 2026 Glow Diary • Feito com criatividade 💗
        </p>

    </footer>

    <script>

        function mudarTema() {
            document.body.classList.toggle("dark");

            const botao = document.querySelector(".tema");

            if (document.body.classList.contains("dark")) {
                botao.textContent = "☀️";
            } else {
                botao.textContent = "🌙";
            }
        }

        function mensagem() {
            alert("✨ Em breve teremos novos conteúdos por aqui!");
        }

    </script>

</body>
</html>
