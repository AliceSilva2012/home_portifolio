<!DOCTYPE html>

<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Home | Alice Silva Pereira</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        body {
            background-color: #0a0a0a; /*Cor de fundo*/
            color: #fff; /*Cor do texto*/
        }

        header {
            display: flex;
            justify-content: center;
            align-items: center;              
        }
        ul {
            display: flex;
            gap: 35px;
            list-style: none;
            font-size: 18px;
            margin-top: 20px;
        }
    /*
        O: align-items 
        só pode ser usado junto de um
        display: flex;
    */
        .principal {
            display: flex;
            align-items: center;
            margin-left: 30px;
            min-height: 65vh;
        }
        .principal div {
            display: flex;
            flex-direction: column;
        }

            /*O mínimo de altura é de mais ou menos 85% da tela no eixo y.
            Por exemplo, 100vh = 100% 
            e como é height(altura), 50vh no eixo y = 50% da altura da tela, a metade da tela.
            */
        .principal h1 {
            font-size: 45px; /*Celular*/
            line-height: 1.1; /*Altura da linha/ texto*/
            margin-bottom: 20px;
            letter-spacing: -2px;
        }
        .principal h1 span {
            color: #FFF01F;
        }
        .principal p {
            font-size: 20px;
            margin-bottom: 20px;
            max-width: 500px;
            color: #bbb;
            margin-bottom: 40px;
        }
        .botao {
            display: inline-block; /*Serve pra alinhar as budega toda*/
            padding: 15px 30px; /*Em cima e embaixo, esquerda e direita*/
            background-color: #FFF01F;
            color: #111;
            font-weight: bold;
            border-radius: 5px;
            width: 85%;
            margin: 0 auto; /*Serve pra centralizar o botão*/
            text-align: center;
            font-size: 18px;
        }
        .botao:hover {
            background-color: #333;
            color: #FFF01F;
            transition: 0.5s;
        }
        span {
            font-weight: bold;
        }
        .secao {
            padding: 100px 0;
        }
        .titulo-secao {
            font-size: 42px;
            margin-bottom: 60px; /*Serve pra afastar os itens debaixo*/
            position: relative;
            border-radius: 30px;
            gap: 30px;
            margin-top: 20px;
        }
        .titulo-secao::after { /*Tudo que eu por aqui vai ter uma posição depois do título "Projetos"*/
            content: ''; /*Isso não define exatamente o objeto, mas o que vai ser feito depois*/
            position: absolute;
            left: 0; /*Vai todo pra esquerda*/
            bottom: -15px; /*Posição*/
            width: 100px; /*Largura da budega*/
            height: 4px; /*Altura da budega*/
            background-color: #FFF01F; /*Cor da budega*/
        }
        .grade-projetos {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .card-projeto {
            background-color: #161616;
            border-radius: 10px;
            overflow: hidden; /*Tira o que ultrapassa os limites de um elemento/ card/ o que cê quiser*/   
            border-radius: 30px;  
            transition: transform 0.3s ease;
        }
        .card-projeto:hover {
            transform: scale(1.05); 
        }
        .card-projeto-ul {
            background-color: #161616;
            border-radius: 30px;
            padding: 18px;
            
            padding-right: 15px; /* aumenta o espaço à direita */     
        } 
        .img-projeto {
            margin-top: 20px; /*Espaço em cima*/
            border-radius: 20px;
            
            display: block;
            margin-left: auto;
            margin-right: auto;
            
            width: 90%;
            height: 200px;
            object-fit: cover; /*Serve pra imagem ocupar o espaço que ela tem pra ocupar.*/
            margin-bottom: 5px; /*Espaço embaixo*/
            gap: 40px;
        }
        .info-projeto {
            padding: 20px;
        }
        .info-projeto h3 {
            color: #fff;
            margin-bottom: 10px;
            font-size: 28px;
        }
        .info-projeto p {
            color: #bbb;
            margin-bottom: 10px;
        }
        .info-projeto a {
            color: #FFF01F;
            font-weight: 500;
        }
        .principal .principal-texto {
            font-size: 16px; 
            margin-left: -10px;
        }
        .sobre {
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }
        .img-sobre {
            height: 380px;
            background-color: #161616;
            border-radius: 10px;
        }
        .conteudo-sobre h2 {
            margin-bottom: 28px;
        }
        .conteudo-sobre p {
            margin-bottom: 20px;
            color: #bbb;
        }
        .habilidades {
            display: flex;
            flex-wrap: wrap; /*Serve pra quebrar a linha se ficar muito grande pra não acabar "quebrando a tela".*/
            margin-top: 20px;
        }
        .tag-habilidades {
            background-color: rgba(255, 220, 0, 0.2);
            color: #FFF01F;
            padding: 8px 15px;
            border-radius: 20px;
            margin-right: 10px;
            margin-bottom: 10px;
            font-size: 14px;
        }
        .botoes-contato {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            align-items: center;
            max-width: 800px;
            margin: 0 auto;
        }
        .botao-contato {
            display: flex;
            gap: 10px;
            padding: 15px 25px;
            border-radius: 10px;
            font-weight: 500;
            min-width: 160px;
            text-decoration: none;
            color: #fff;
            
        }
        .whatsapp {
            background-color: #25d366;
        }
        .email {
            background-color: #ea4335;
        }
        .github {
            background-color: #333;
        }
    
        .footer {
            padding: 20% 5%;
            text-align: center;
            border-top: 1px solid #333;
        }
        .efeito-cursor {
            cursor: pointer;
            transition: transform 0.4s ease-in-out;
        }
        .efeito-cursor:hover {
            transform: translateY(-10px);
        }
        .point {
            pointer-events: none; /*Pra usuários de pc isso tira a setinha*/
            position: fixed;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            background-color: rgba(255, 240, 31, 0.65);
            z-index: 99;
            /*transform: translate(-50%, -50%);*/
        }
        /* Tablet */
        @media (min-width: 768px) {
            .principal h1 {
                font-size: 56px;
            }
            .principal p {
                font-size: 22px;
            }
        }

/* Notebook */
        @media (min-width: 1024px) { 
            ul {
                font-size: 32px;
                gap: 55px;
            }
            .principal h1 {
                font-size: 64px;
                margin-bottom: 30px;
            }
            .principal p {
                font-size: 24px;
                max-width: 650px;
                line-height: 1.6;
             }
            .principal {
                min-height: 75vh;
                padding: 0 80px;
                margin-left: 0;
            }
            .sobre {
                grid-template-columns: 1fr 1fr;
            }
        }
          
/* Desktop */
        @media (min-width: 1440px) {
            .principal h1 {
                font-size: 72px;
             }
            .principal p {
                font-size: 26px;
                max-width: 650px;
            }
        }
        footer p {
            text-align: center;
            margin-top: 20px;
            margin-bottom: 20px;
            font-size: 18px;
        }
        footer hr {
            width: 90%;
            display: flex;
            margin: 20px auto;
            border: 1px solid #555;
        }
        .footer-span {
            font-weight: bold;
            color: #FFF01F;
        }
    </style>
</head>
<body>
    <header>
        <ul class="card-projeto-ul">
            <li>
                <a>Home</a>
            </li>
            <li>
                <a>Projetos</a>
            </li>
            <li>
                <a>Sobre</a>
            </li>
            <li>
                <a>Contato</a>
            </li>
        </ul>
    </header>  
    <section>
        <div class="principal">
           <div>
                <h1>Olá, eu sou <br><span>Alice Silva Pereira</span>!</h1>
                <p class="principal-texto">Estudante de programação com foco em desenvolvimento web. Crio projetos utilizando <span>HTML</span>, <span>CSS</span> e <span>JavaScript</span>, buscando construir interfaces responsivas, funcionais pensando em uma boa experiência para o usuário.</p>
                <a class="botao">Ver projetos</a>
           </div>
        </div>
    </section>
    <section class="projetos">
        <h2 class="titulo-secao">Projetos</h2>
        <div class="grade-projetos">
            <div class="card-projeto">
                <img class="img-projeto" src="https://s3-figma-hubfile-images-production-cdn-cgi.figma.com/cdn-cgi/image/format=auto,quality=auto,width=800,height=480/hub/file/carousel/img/c2413e0d3d046a1fa3330b6717a6bd6bd3cab324" alt="pokedex imagem">
                  <div class="info-projeto">
                      <h3>Pokédex</h3>
                      <p>A Pokédex é um projeto que permite pesquisar um Pokémon por nome ou número, navegar entre eles pelos botões de anterior e próximo (a partir do Pokémon #001) e exibir informações e sprites animados de forma dinâmica. Durante o desenvolvimento, foram praticados conceitos como manipulação de DOM, consumo de APIs com fetch, programação assíncrona (async/await), tratamento básico de erros e criação de uma interface responsiva inspirada na Pokédex dos jogos clássicos de Pokémon.</p>
                      <a href="pokedex.html">Ver projeto</a>
                  </div>
            </div>
            <div class="card-projeto">
                <img class="img-projeto" src="https://www.nordinvestimentos.com.br/cdn-cgi/imagedelivery/WVyV4OkToIxntlRloKFH7Q/blog/uploads/debfc142-afab-40a7-9897-b3d5a1927658/melhor-servico-de-streaming.jpg/format=auto,w=785,h=442" alt="steamhub imagem">
                  <div class="info-projeto">
                      <h3>SteamHUB</h3>
                      <p>O SteamHUB, uma página web baseada em serviços de streaming utilizando <span>HTML, CSS e JavaScript</span>. O projeto exibe filmes, séries, animes e desenhos animados em categorias com cards interativos, layout responsivo com rolagem estilo carrosel, efeitos visuais e links direcionados ao site 'IMDb' para demais informações.</p>
                      <a href="steamHub.html">Ver projeto</a>
                 </div>
            </div>
            <div class="card-projeto">
                <img class="img-projeto" src="https://www.exitlag.com/blog/wp-content/uploads/2025/01/Games-Like-Roblox_-Top-Alternatives-for-Roblox-Fans.webp" alt="pixelhub imagem">
                  <div class="info-projeto">
                      <h3>PixelHUB</h3>
                      <p>O PixelHUB é uma página web em formato de catálogo de jogos, onde diversos títulos são exibidos por meio de cards gerados dinamicamente a partir de um array em <span>JavaScript</span>, apresentando informações como imagem, gênero, sinopse, avaliações e link para o site oficial. O projeto destaca conceitos de manipulação do DOM, organização de dados em objetos, responsividade básica e estilização com uma interface inspirada na identidade visual de cada jogo.</p>
                      <a href="pixelHub.html">Ver projeto</a>
                 </div>
            </div>
        </div>
    </section>
    <section class="secao">
        <h2 class="titulo-secao">Sobre mim</h2>
</h2>
        <div class="sobre">
            <img class="img-sobre" src="https://cloudpfp.com/wp-content/uploads/2026/06/cat-minecraft-pfp-1.webp" alt="imagem de perfil">
            <div class="conteudo-sobre">
                <h2>Sobre minha Jornada</h2>
                <p>Sou estudante de programação. Comecei a aprender <span>HTML, CSS e JavaScript</span> em <span>2026</span>, por conta própria. Tenho vontade de explorar tanto o caminho back-end quanto front-end e tenho interesse em seguir na área de desenvolvimento <span>Full-stack</span>.</p>
                <p>Estou sempre buscando evoluir minhas habilidades e aprender novas tecnologias. Tenho interesse em seguir na área de desenvolvimento Full-stack, unindo conhecimentos de front-end e back-end para criar soluções completas.</p>
                <div class="habilidades">
                    <span class="tag-habilidades">HTML5</span>
                    <span class="tag-habilidades">CSS3</span>
                    <span class="tag-habilidades">JavaScript</span>
                    <span class="tag-habilidades">UX/UI</span>
                </div>
            </div>
        </div>
    </section>
    <section class="secao">
        <h2 class="titulo-secao">Contato</h2>
        <div class="botoes-contato">
            <a href="https://wa.me/5511917953772" target="_blank" rel="noopener" class="botao-contato whatsapp efeito-cursor">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-label="WhatsApp">
                    <path d="M12 2C6.48 2 2 6.28 2 11.56C2 13.64 2.7 15.58 3.9 17.18L2.5 22L7.55 20.65C8.93 21.35 10.42 21.72 12 21.72C17.52 21.72 22 17.44 22 12.16C22 6.88 17.52 2 12 2Z" stroke="white" stroke-width="2" stroke-linejoin="round"/>
                    <path d="M8.5 8.5C8.8 8.1 9.2 8.1 9.5 8.5L10.7 10.1C11 10.5 11 10.9 10.7 11.2L10.1 11.8C10.9 13.2 12 14.3 13.5 14.9L14 14.3C14.3 14 14.7 14 15.1 14.3L16.6 15.5C17 15.8 17 16.2 16.7 16.6C16.2 17.3 15.4 17.7 14.6 17.5C11.2 16.8 7.2 12.8 6.5 9.4C6.3 8.6 7.1 8.8 8.5 8.5Z" fill="white"/>
                </svg>
                <span>WhatsApp</span>
            </a>
            <a href="mailto:alice.pereira3@portalsesisp.com.br" class="botao-contato email efeito-cursor">             
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-label="Email">
                    <path d="M3 5.5C3 4.67 3.67 4 4.5 4H19.5C20.33 4 21 4.67 21 5.5V18.5C21 19.33 20.33 20 19.5 20H4.5C3.67 20 3 19.33 3 18.5V5.5Z" stroke="white" stroke-width="2" stroke-linejoin="round"/>
                    <path d="M4 6L12 13L20 6" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <span>E-mail</span>
            </a>
            <a href="https://github.com/AliceSilva2012" target="_blank" rel="noopener" class="botao-contato github efeito-cursor">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="white" xmlns="http://www.w3.org/2000/svg" aria-label="GitHub">
                    <path d="M12 2C6.48 2 2 6.58 2 12.22C2 16.72 4.87 20.54 8.84 21.89C9.34 21.99 9.52 21.67 9.52 21.39C9.52 21.14 9.51 20.42 9.51 19.47C6.88 20.05 6.21 18.32 6.21 18.32C5.76 17.15 5.1 16.84 5.1 16.84C4.22 16.23 5.17 16.24 5.17 16.24C6.14 16.31 6.65 17.26 6.65 17.26C7.52 18.78 8.93 18.34 9.56 18.06C9.65 17.4 9.9 16.96 10.18 16.71C8.08 16.46 5.87 15.64 5.87 11.69C5.87 10.56 6.26 9.64 6.89 8.92C6.78 8.66 6.44 7.61 7 6.19C7 6.19 7.82 5.92 9.5 7.08C10.29 6.86 11.15 6.75 12 6.75C12.85 6.75 13.71 6.86 14.5 7.08C16.18 5.92 17 6.19 17 6.19C17.56 7.61 17.22 8.66 17.11 8.92C17.74 9.64 18.13 10.56 18.13 11.69C18.13 15.65 15.92 16.45 13.82 16.7C14.17 17 14.48 17.6 14.48 18.51C14.48 19.82 14.47 20.87 14.47 21.39C14.47 21.67 14.65 21.99 15.15 21.89C19.13 20.54 22 16.72 22 12.22C22 6.58 17.52 2 12 2Z"/>
                </svg>
                <span>GitHub</span>
            </a>
        </div>
    </section>
    <footer>
        <hr>
        <p>Feito por <span class="footer-span">Alice Silva Pereira</span>!</p>
    </footer>
    <div class="point"></div>
    <script>
        const cursor = document.querySelector('.point');

        document.addEventListener('mousemove', function(info) {
            if(cursor) {
                cursor.style.left = info.clientX + 'px';
                cursor.style.top = info.clientY + 'px';
            }
        });
    </script>
</body>
</html>
