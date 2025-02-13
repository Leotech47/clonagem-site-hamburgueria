# Analise do código-fonte do site: https://primeburgeria1.netlify.app/

## Código fonte:

<!DOCTYPE html>
<html lang="pt-br">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <script src="https://cdn.tailwindcss.com"></script>
    <script
        src="https://cdn.tailwindcss.com?plugins=forms,typography,aspect-ratio,line-clamp,container-queries"></script>
    <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/toastify-js/src/toastify.min.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"
        integrity="sha512-Fo3rlrZj/k7ujTnHg4CGR2D7kSs0v4LLanw2qksYuRlEzO+tcaEPQogQ0KaoGN26/zrn20ImR1DfuLWnOo7aBA=="
        crossorigin="anonymous" referrerpolicy="no-referrer" />
    <link rel="shortcut icon" href="/src/img/Icones/comida-rapida.png"> <!--aparece o simbolo da hamburgeria-->

    <!-- META TAG OG -->
    <meta property="og:type" content="website" />
    <meta property="og:title" content="Prime Burgeria" />
    <meta property="og:image" content="https://primeburgeria.netlify.app/src/img/Logo.webp" />
    <meta property="og:description" content="O melhor Hambúrguer da região!" />
    <meta property="og:site_name" content="PrimeBurgeria" />

    <!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-BGCT0DLS42"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag() { dataLayer.push(arguments); }
        gtag('js', new Date());

        gtag('config', 'G-BGCT0DLS42');
    </script>




    <title>PrimeBurgeria</title>
</head>




<script>
    tailwind.config = {
        theme: {
            extend: {
                colors: {
                    'nav': '#343734',
                    'fundo': '#FFF5EB',
                    'prime-brown': '#333333',
                    'prime-gold': '#FFBB55',
                    'prime-laranja': '#EFC17F', <!--testando a cor-->
                    'prime-hover': '#F76D5E',
                    'prime-price': '#00A676',
                    'prime-border': '#EDEDED'
                },
                backgroundImage: {
                    home: "url('../src/img/fundo.png')",
                }

            }
        }
    }
</script>


<body class=" overflow-x-hidden w-full">
    <!--HEADER-->
    <div id="home"></div>
    <header class="bg-nav h-19 fixed z-50 w-full top-0 left-0">
        <nav class="flex items-center justify-between w-[92%] mx-auto">
            <div class="flex items-center gap-2">
                <a onclick="onToggleMenu(this)" name="menu" class="h-6 w-6 cursor-pointer md:hidden"><img
                        src="/src/img/Icones/icons8-hambúrguer-50.png" alt=""></a>
                <a class='logo-link transition-opacity duration-300' href='/'>
                    <img class="w-16 h-16 mx-auto cursor-pointer rounded-full mt-1 mb-1"
                        src="./src/img/logo-removebg-preview.png" alt="Prime Burgeria Logo">
                </a>
            </div>

            <div
                class="nav-links bg-nav md:static fixed md:min-h-fit min-h-screen left-[-100%] top-0 w-[70%] md:w-auto flex items-center px-5 transition-all duration-300 ease-in-out md:translate-x-0 shadow-2xl md:shadow-none">
                <!-- Cabeçalho do menu mobile com logo e botão fechar -->
                <div class="absolute top-4 left-4 right-4 flex justify-between items-center md:hidden">
                    <img class="w-16 h-16 rounded-full" src="./src/img/logo-removebg-preview.png"
                        alt="Prime Burgeria Logo">
                    <a onclick="onToggleMenu(this)" name="close" class="h-6 w-6 cursor-pointer text-white"><img
                            src="/src/img/Icones/icons8-x-50 (1).png" alt=""></a>

                </div>

                <div class="flex flex-col w-full">
                    <ul
                        class="flex md:flex-row flex-col md:items-center md:gap-[2vw] lg:gap-6 gap-4 w-full md:mt-0 mt-16">
                        <li>
                            <a class='text-2xl text-white hover:text-prime-gold transition-colors duration-300 flex items-center gap-2' href='/'>
                                <img src="/src/img/Icones/icons8-casa-64.png" alt="Home" class="w-6 h-6">
                                Home
                            </a>
                        </li>
                        <li>
                            <a class='text-2xl text-white hover:text-prime-gold transition-colors duration-300 flex items-center gap-2' href='/src/page/menu'>
                                <img src="/src/img/Icones/icons8-menu-de-restaurante-50.png" alt="Menu" class="w-6 h-6">
                                Menu
                            </a>
                        </li>
                        <li>
                            <a class="text-2xl text-white hover:text-prime-gold transition-colors duration-300 flex items-center gap-2"
                                href="#sobre-nos">
                                <img src="/src/img/Icones/icons8-sobre-52.png" alt="Sobre Nós" class="w-6 h-6">
                                Sobre
                            </a>
                        </li>
                        <li>
                            <a class="text-2xl text-white hover:text-prime-gold transition-colors duration-300 flex items-center gap-2"
                                href="#Assessment">
                                <img src="/src/img/Icones/icons8-estrela-24.png" alt="Avaliação" class="w-6 h-6">
                                Avaliação
                            </a>
                        </li>
                        <li>
                            <a class="text-2xl text-white hover:text-prime-gold transition-colors duration-300 flex items-center gap-2"
                                href="#endereço">
                                <img src="/src/img/Icones/icons8-marcador-32.png" alt="Endereço" class="w-6 h-6">
                                Endereço
                            </a>
                        </li>

                    </ul>

                    <!-- Login e Carrinho (visíveis apenas em mobile) -->
                    <div class="flex flex-col gap-4 mt-8 md:hidden">
                        <a class='flex items-center gap-2 text-prime-laranja' href='/src/page/login'>
                            <img src="/src/img/Icones/icons8-pessoa-32.png" class="w-6 h-6" alt="login">
                            <span class="text-xl text-white">Login</span>
                        </a>

                        <button class="flex items-center gap-2 text-prime-laranja" id="cart-btn-mobile">
                            <img src="/src/img/Icones/icons8-carrinho-de-compras-100.png" class="w-8 h-8"
                                alt="carrinho">
                            <span class="text-xl text-white">Carrinho</span>
                            <span id="cart-count-mobile" class=" text-white px-2 py-1 rounded-full text-sm">0</span>
                        </button>
                    </div>
                </div>
            </div>

            <!-- LOGIN e CARRINHO (visíveis apenas em desktop) -->
            <div class="hidden md:flex items-center gap-6">
                <a href='/src/page/login'>
                    <button class="flex items-end gap-2 text-black font-bold">
                        <img src="/src/img/Icones/icons8-pessoa-32.png" alt="LOGIN">
                    </button>
                </a>
                <button class="flex items-center gap-2 text-white font-bold" id="cart-btn">
                    <span id="cart-count">0</span>
                    <img src="/src/img/Icones/icons8-carrinho-de-compras-100.png" class="w-10 h-10" alt="carrinho">
                </button>
            </div>
        </nav>
    </header>


    <main class=" py-8 pt-24">
        <!-- Promoções da Semana -->
        <section class="max-w-7xl mx-auto px-4">
            <div class="mb-8">
                <h2 class="text-2xl md:text-3xl font-bold text-center mb-6 text-prime-brown">
                    PROMOÇÕES DA <span class="text-prime-gold">SEMANA</span>
                </h2>

                <div class="flex flex-wrap gap-3 justify-center md:flex-wrap md:justify-between ">
                    <!-- Segunda -->
                    <article class="bg-white rounded-lg shadow-lg p-4  mx-auto max-w-md">
                        <img src="./src/img/promoção/segunda.png" alt="Promoção de Segunda"
                            class="w-80 h-48 object-fill rounded-t-lg">
                        <div class="p-4 text-center">
                            <h3 class="font-bold text-lg">Segunda-feira</h3>
                            <p class="text-prime-gold font-bold">Compre 1 Leve 2</p>
                            <p class="text-gray-600"></p>
                            <button id="promo-segunda"
                                class="bg-prime-gold text-white px-4 py-2 rounded mt-4 w-full add-to-cart-btn hover:bg-prime-brown transition-colors duration-300 hidden"
                                data-name="Promoção Segunda - Compre 1 Leve 2" data-price="18.90">
                                Adicionar ao Carrinho
                            </button>
                        </div>
                    </article>

                    <!-- Quarta -->
                    <article class="bg-white rounded-lg shadow-lg p-4 mx-auto max-w-md">
                        <img src="./src/img/promoção/quarta.png" alt="Promoção de Quarta"
                            class="w-80 h-48 object-fill rounded-t-lg">
                        <div class="p-4 text-center">
                            <h3 class="font-bold text-lg">Quarta-feira</h3>
                            <p class="text-prime-gold font-bold">Combo Família</p>
                            <p class="text-gray-600">4 hambúrgueres + 1 Coca de 2l R$89,90</p>
                            <button id="promo-quarta"
                                class="bg-prime-gold text-white px-4 py-2 rounded mt-4 w-full add-to-cart-btn hover:bg-prime-brown transition-colors duration-300 hidden"
                                data-name="Combo Família - 4 Hambúrgueres + 4 Bebidas" data-price="89.90">
                                Adicionar ao Carrinho
                            </button>
                        </div>
                    </article>

                    <!-- Sexta -->
                    <article class="bg-white rounded-lg shadow-lg p-4 mx-auto max-w-md">
                        <img src="./src/img//promoção/sexta.png" alt="Promoção de Sexta"
                            class="w-80 h-48 object-fill rounded-t-lg">
                        <div class="p-4 text-center">
                            <h3 class="font-bold text-lg">Sexta-feira</h3>
                            <p class="text-prime-gold font-bold">Combo Trio</p>
                            <p class="text-gray-600">R$25,90</p>
                            <button id="promo-sexta"
                                class="bg-prime-gold text-white px-4 py-2 rounded mt-4 w-full add-to-cart-btn hover:bg-prime-brown transition-colors duration-300 hidden"
                                data-name="Combo Trio" data-price="25.90">
                                Adicionar ao Carrinho
                            </button>
                        </div>
                    </article>
                </div>
            </div>
        </section>
    </main>

    <!--INICIO CARD-->
    <section class="w-full h-[420px] bg-home relativo flex flex-col justify-center items-center">
        <img src="./src/img/Logo.webp" alt="Logo Prime Burgeria"
            class="w-32 h-32 rounded-full shadow-lg hover:scale-110 duration-200"><br>

        <span class="text-white font-medium">Rua 57, Valparaíso de Goiás </span>
        <div class="bg-green-600 px-4 py-1 rounded-lg mt-5" id="date-span">
            <span class="text-white font-medium">Seg á Dom - 18:00 ás 23:30</span>
        </div>
    </section>


    <!--INICIO DO SOBRE NÓS-->
    <h1 class="text-2xl md:text-3xl font-bold text-center mt-9 mb-6 text-prime-brown">
        SOBRE <span class="text-prime-gold">NÓS</span>
    </h1>

    <section id="sobre-nos"
        class="grid grid-cols-1 md:grid-cols-2 gap-7 md:gap-10 mx-auto max-w-7xl px-2 mb-16 scroll-mt-32 pt-5 items-center md:items-center">

        <article>
            <img class="rounded-md lg:w-full" src="./src/img/Loja.webp" alt="frente da loja">

        </article>

        <article>
            <p class="py-6 md:text-base text-lg text-gray-700">


                A Prime Burgeria nasceu da paixão por hambúrgueres de qualidade. Seu fundador queria criar um lugar onde
                cada hambúrguer fosse feito com ingredientes frescos e premium, com o cuidado de uma refeição caseira.
                Desde o início, a Prime Burgeria se destacou pelo compromisso com a excelência e o atendimento caloroso.
                <br>

                Hoje, é o ponto de encontro para quem busca um hambúrguer único e uma experiência especial. Na Prime
                Burgeria, cada cliente é tratado como parte da família, e cada hambúrguer é preparado para ser mais do
                que uma refeição: uma lembrança deliciosa.
            </p>
        </article>
    </section>
    <!--FIM DO SOBRE NÓS-->

    <!--INICIO AVALIAÇÃO-->
    <h1 class="text-2xl md:text-3xl font-bold text-center mt-9 mb-6 text-prime-brown">
        AVALIAÇÃO
    </h1>
    <section id="Assessment"
        class=" py-8 scroll-mt-32 pt-5 grid grid-cols-1 md:grid-cols-2 gap-7 md:gap-10 mx-auto max-w-7xl px-2 mb-16">
        <!--INICIO CARD COMENTÁRIO-->
        <article>
            <h6 class="text-center font-bold">João Pedro</h6>

            <div class="bg-white p-4 border-solid border-1 shadow-2xl rounded text-gray-700 ">
                <p>A Prime Burgeria me surpreendeu! Ambiente aconchegante, hambúrguer suculento e bem temperado, com
                    atendimento rápido e simpático. Já virou meu lugar favorito!</p>
            </div>

        </article>

        <!--INICIO CARD COMENTÁRIO-->
        <article>
            <h6 class="text-center font-bold">Samuel Pantoja</h6>

            <div class="bg-white p-4 border-solid border-1 shadow-2xl rounded text-gray-700 ">
                <p>Experiência incrível na Prime Burgeria! Hambúrguer caprichado, batatas crocantes e atendimento ótimo.
                    Dá pra sentir o cuidado em cada detalhe. Recomendo demais!</p>
            </div>

        </article>
    </section>
    <!--FIM AVALIAÇÃO-->

    <!--INICIO LOCALIZAÇÃO-->
    <section id="endereço" class="bg-white py-8">
        <h2 class="text-2xl md:text-3xl font-bold text-center mb-6 text-prime-brown">
            Localização
        </h2>

        <div class="mx-auto px-4 py-4 flex items-center justify-center">
            <div class="w-full max-w-4xl">
                <!-- Wrapper do mapa com placeholder -->
                <div class="map-container relative w-full" style="padding-bottom: 56.25%;">
                    <!-- Placeholder enquanto o mapa carrega -->
                    <div class="absolute inset-0 bg-gray-200 animate-pulse flex items-center justify-center">
                        <p class="text-gray-500">Carregando mapa...</p>
                    </div>

                    <!-- iframe do mapa com loading lazy -->
                    <iframe class="absolute top-0 left-0 w-full h-full rounded-lg shadow-lg"
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3834.9833996590532!2d-48.07191319763663!3d-16.014379634494944!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x935bd54d87817147%3A0x43018ff6374e44b7!2sGel%C3%A9ia%20Burger!5e0!3m2!1spt-BR!2sbr!4v1730949463185!5m2!1spt-BR!2sbr"
                        loading="lazy" referrerpolicy="no-referrer-when-downgrade"
                        title="Localização da Prime Burgeria">
                    </iframe>
                </div>

                <!-- Informações de endereço -->
                <div class="mt-4 text-center">
                    <p class="text-gray-700">A Localização foi pra efeito de estudo</p>
                    <p class="text-gray-700">Pois a Prime Burgeria e fictícia. </p>
                </div>
            </div>
        </div>
    </section>
    <!--FIM LOCALIZAÇÃO-->


    <!--BUTTON CART FOOTER-->
    <footer class="w-full bg-nav py-2 bottom-0 z-40 flex items-center justify-center">
        <p class="flex justify-center text-prime-laranja text-center font-semibold flex-wrap">
            Copyright &copy; Todos os Direitos Reservados | Desenvolvido por:
            <span class="ml-1">
                <a href="https://wa.me/5561981500971" target="_blank"
                    class="text-prime-laranja no-underline cursor-pointer">
                    Dev Natanael
                </a>
            </span>
        </p>


    </footer>
    <!-- FIM BUTTON CART FOOTER-->

    <!--MODAL CART-->
    <section class="bg-black/60 w-full h-full fixed top-0 left-0 z-50 items-center justify-center hidden"
        id="cart-modal">
        <article class="bg-white p-5 rounded-md min-w-[90%] md:min-w-[600px] max-h-[90vh] overflow-y-auto">
            <h2 class="text-center font-bold text-2x1 mb-2">Meu carrinho</h2>

            <div class="mt-4">
                <label class="flex items-center">
                    <input type="checkbox" id="pickup-option" class="mr-2">
                    <span>Retirar no Local</span>
                </label>
            </div>

            <div class="flex justify-between mb-2 flex-col" id="cart-items"></div>
            <p class="font-bold mt-2"><span id="cart-total"></span></p>


            <p class="font-bold mt-4">Endereço de entrega</p>
            <input type="text" placeholder="Digite seu endereço completo..." id="address"
                class="w-full border-1 p-1 rounded my-1">
            <p class="text-red-500 hidden" id="address-warn">Digite seu endereço completo!</p>

            <div class="flex items-center justify-between mt-5 w-full">
                <button id="close-modal-btn">Fechar</button>
                <button id="checkout-btn" class="bg-green-500 text-white px-4 py-1 rounded">Finalizar pedido</button>
            </div>
        </article>
    </section>



    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/toastify-js"></script>
    <script src="/src/js/script.js"></script>
</body>

</html>

---

**1. Estrutura de Pastas e Arquivos:**

```
PrimeBurgeria/
│-- index.html  # Página principal
│-- src/
│   ├── img/
│   │   ├── Icones/
│   │   │   ├── comida-rapida.png
│   │   │   ├── icons8-hambúrguer-50.png
│   │   │   ├── icons8-x-50.png
│   │   │   ├── icons8-casa-64.png
│   │   │   ├── icons8-menu-de-restaurante-50.png
│   │   │   ├── icons8-sobre-52.png
│   │   │   ├── icons8-estrela-24.png
│   │   │   ├── icons8-marcador-32.png
│   │   │   ├── icons8-pessoa-32.png
│   │   │   ├── icons8-carrinho-de-compras-100.png
│   │   ├── Logo.webp
│   │   ├── logo-removebg-preview.png
│   │   ├── fundo.png
│   │   ├── Loja.webp
│   │   ├── promoção/
│   │   │   ├── segunda.png
│   │   │   ├── quarta.png
│   │   │   ├── sexta.png
│   ├── page/
│   │   ├── menu.html
│   │   ├── login.html
│-- styles/
│   ├── main.css  # Folha de estilos personalizada
│-- scripts/
│   ├── main.js   # Scripts JS personalizados
```

**2. Explicação do Código-Fonte:**

O código HTML apresentado pertence a um site de uma hamburgueria chamada "PrimeBurgeria". Ele contém as seguintes seções principais:

### **Cabeçalho (<head>)**
- Declaração do tipo de documento (`<!DOCTYPE html>`) e idioma (`<html lang="pt-br">`).
- Definição da codificação (`UTF-8`) e da configuração de viewport para responsividade.
- Importação da biblioteca TailwindCSS para estilização dinâmica.
- Importação da biblioteca Toastify para notificações visuais.
- Uso do Google Fonts para carregamento da fonte "Roboto".
- Inclusão do FontAwesome para ícones.
- Definição de ícone (favicon) da hamburgueria.
- Meta tags Open Graph (`og:`) para melhor exibição do site ao ser compartilhado.
- Inclusão do Google Analytics para rastreamento de acessos.
- Definição da configuração de cores personalizadas via TailwindCSS (`tailwind.config`).

### **Corpo (<body>)**

#### **1. Cabeçalho fixo (Navbar)**
- Contém a logo e um menu de navegação com links para as seções: Home, Menu, Sobre, Avaliação e Endereço.
- O menu é responsivo, ajustando-se para dispositivos móveis.
- Possui botões de login e carrinho de compras.

#### **2. Seção Principal (<main>)**
##### **Promoções da Semana**
- Três artigos (`<article>`) destacam promoções para segunda, quarta e sexta-feira.
- Cada promoção tem:
  - Uma imagem do produto.
  - Um título com o dia da promoção.
  - Uma breve descrição da oferta.
  - Um botão oculto para adicionar o item ao carrinho.

##### **3. Seção Informativa**
- Mostra a logo da hamburgueria e seu endereço.
- Indica o horário de funcionamento.

##### **4. Seção "Sobre Nós"**
- Exibe uma imagem da loja e um texto sobre a história e filosofia da hamburgueria.

##### **5. Seção "Avaliação"**
- Exibe dois depoimentos de clientes satisfeitos dentro de `<article>`.
- Cada comentário está dentro de uma caixa (`div`) estilizada.

##### **6. Seção "Localização"**
- Exibe um mapa do Google Maps incorporado (`<iframe>`), indicando a localização física da loja.

### **Conclusão**
Este código cria uma página inicial moderna e responsiva para a "PrimeBurgeria", utilizando TailwindCSS para estilos, JavaScript para interatividade e Google Analytics para rastreamento. O site foca na experiência do usuário com um design intuitivo, promovendo os produtos e facilitando a navegação.

