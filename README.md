Novatrend-Brasil/
│
├── index.html
├── produtos.html
├── produto.html
├── carrinho.html
├── checkout.html
├── login.html
├── contato.html
├── sobre.html
│
├── css/
│   ├── style.css
│   ├── home.css
│   ├── produto.css
│   ├── checkout.css
│   └── responsivo.css
│
├── js/
│   ├── app.js
│   ├── carrinho.js
│   ├── produtos.js
│   ├── busca.js
│   └── login.js
│
├── imagens/
├── icones/
└── assets/
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Novatrend Brasil | Loja Oficial</title>

<link rel="stylesheet" href="css/style.css">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
</head>

<body>

<header>

<div class="logo">
<h1>Novatrend Brasil</h1>
</div>

<nav>

<a href="#">Início</a>
<a href="#">Categorias</a>
<a href="#">Ofertas</a>
<a href="#">Contato</a>

</nav>

<div class="icons">

<button>🔍</button>

<button>❤️</button>

<button>🛒</button>

</div>

</header>

<section class="hero">

<h2>Os produtos mais desejados da internet.</h2>

<p>
Qualidade, preço baixo e entrega para todo o Brasil.
</p>

<a href="#" class="btn">
Comprar Agora
</a>

</section>

<section class="produtos">

<h2>Produtos em Destaque</h2>

<div class="grid">

<div class="card">
<img src="https://via.placeholder.com/300x250" alt="">
<h3>Smartwatch Ultra</h3>
<p>R$ 199,90</p>
<button>Comprar</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/300x250" alt="">
<h3>Fone Bluetooth</h3>
<p>R$ 89,90</p>
<button>Comprar</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/300x250" alt="">
<h3>Mini Projetor</h3>
<p>R$ 399,90</p>
<button>Comprar</button>
</div>

</div>

</section>

<footer>

<p>© 2026 Novatrend Brasil - Todos os direitos reservados.</p>

</footer>

<script src="js/script.js"></script>

</body>
</html>
