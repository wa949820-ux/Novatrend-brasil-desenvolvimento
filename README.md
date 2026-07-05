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
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    background:#f7f7f7;
    color:#222;
}

header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:20px 8%;
    background:#111;
    color:#fff;
    position:sticky;
    top:0;
}

.logo h1{
    color:#ff9800;
}

nav a{
    color:white;
    margin:0 15px;
    text-decoration:none;
    transition:.3s;
}

nav a:hover{
    color:#ff9800;
}

.icons button{
    background:none;
    border:none;
    color:white;
    font-size:22px;
    cursor:pointer;
    margin-left:15px;
}

.hero{
    height:70vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    background:linear-gradient(135deg,#111,#333);
    color:white;
    padding:20px;
}

.hero h2{
    font-size:48px;
    margin-bottom:20px;
}

.hero p{
    font-size:20px;
    margin-bottom:30px;
}

.btn{
    background:#ff9800;
    color:white;
    padding:15px 35px;
    border-radius:40px;
    text-decoration:none;
    font-weight:bold;
    transition:.3s;
}

.btn:hover{
    background:#e68900;
}

.produtos{
    padding:70px 8%;
}

.produtos h2{
    text-align:center;
    margin-bottom:40px;
    font-size:34px;
}

.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:25px;
}

.card{
    background:white;
    border-radius:15px;
    overflow:hidden;
    box-shadow:0 10px 25px rgba(0,0,0,.08);
    transition:.3s;
}

.card:hover{
    transform:translateY(-8px);
}

.card img{
    width:100%;
}

.card h3{
    padding:15px;
}

.card p{
    padding:0 15px;
    color:#ff9800;
    font-size:22px;
    font-weight:bold;
}

.card button{
    width:90%;
    margin:20px auto;
    display:block;
    padding:12px;
    border:none;
    background:#111;
    color:white;
    border-radius:8px;
    cursor:pointer;
}

footer{
    background:#111;
    color:white;
    text-align:center;
    padding:30px;
    margin-top:60px;
}

@media(max-width:768px){

header{
    flex-direction:column;
    gap:15px;
}

.hero h2{
    font-size:34px;
}

nav{
    display:flex;
    flex-wrap:wrap;
    justify-content:center;
}

}document.querySelectorAll(".card button").forEach(botao=>{
    botao.addEventListener("click",()=>{
        alert("Em breve você poderá adicionar este produto ao carrinho.");
    });
});
let carrinho = JSON.parse(localStorage.getItem("carrinho")) || [];

const botoes = document.querySelectorAll(".card button");

botoes.forEach((botao) => {
    botao.addEventListener("click", () => {

        const card = botao.parentElement;

        const produto = {
            nome: card.querySelector("h3").innerText,
            preco: card.querySelector("p").innerText,
            imagem: card.querySelector("img").src
        };

        carrinho.push(produto);

        localStorage.setItem("carrinho", JSON.stringify(carrinho));

        atualizarCarrinho();

        alert(produto.nome + " foi adicionado ao carrinho!");
    });
});

function atualizarCarrinho() {

    let contador = document.getElementById("contadorCarrinho");

    if(contador){
        contador.innerText = carrinho.length;
    }

}

window.onload = atualizarCarrinho;
<button>🛒</button><button>
🛒 <span id="contadorCarrinho">0</span>
</button>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Carrinho | Novatrend Brasil</title>

<link rel="stylesheet" href="css/style.css">

<style>
.carrinho{
max-width:1200px;
margin:auto;
padding:50px 20px;
}

.item{
display:flex;
justify-content:space-between;
align-items:center;
background:white;
padding:20px;
margin-bottom:20px;
border-radius:12px;
box-shadow:0 5px 15px rgba(0,0,0,.08);
}

.item img{
width:90px;
height:90px;
object-fit:cover;
border-radius:10px;
}

.info{
flex:1;
margin-left:20px;
}

.info h3{
margin-bottom:10px;
}

button{
background:#e53935;
color:white;
border:none;
padding:10px 20px;
border-radius:8px;
cursor:pointer;
}

.total{
text-align:right;
font-size:28px;
font-weight:bold;
margin-top:30px;
}

.finalizar{
display:block;
width:100%;
padding:18px;
background:#25D366;
color:white;
text-align:center;
text-decoration:none;
border-radius:12px;
margin-top:30px;
font-size:20px;
}
</style>

</head>

<body>

<header>
<h1>🛒 Meu Carrinho</h1>
</header>

<section class="carrinho">

<div id="listaProdutos"></div>

<div class="total">
Total: <span id="total">R$ 0,00</span>
</div>

<a href="checkout.html" class="finalizar">
Finalizar Compra
</a>

</section>

<script src="js/carrinho.js"></script>

</body>
</html>const lista=document.getElementById("listaProdutos");
const total=document.getElementById("total");

let carrinho=JSON.parse(localStorage.getItem("carrinho"))||[];

function carregar(){

lista.innerHTML="";

let soma=0;

carrinho.forEach((produto,index)=>{

const valor=parseFloat(produto.preco.replace("R$","").replace(",","."));

soma+=valor;

lista.innerHTML+=`

<div class="item">

<img src="${produto.imagem}">

<div class="info">

<h3>${produto.nome}</h3>

<p>${produto.preco}</p>

</div>

<button onclick="remover(${index})">

Remover

</button>

</div>

`;

});

total.innerHTML="R$ "+soma.toFixed(2).replace(".",",");

}

function remover(index){

carrinho.splice(index,1);

localStorage.setItem("carrinho",JSON.stringify(carrinho));

carregar();

}

carregar();
const carrinho = JSON.parse(localStorage.getItem("carrinho")) || [];

let total = 0;

carrinho.forEach(produto => {
    total += parseFloat(
        produto.preco.replace("R$", "").replace(",", ".")
    );
});

document.getElementById("quantidade").innerHTML =
"Produtos: " + carrinho.length;

document.getElementById("valorTotal").innerHTML =
"Total: R$ " + total.toFixed(2).replace(".", ",");

function finalizarPedido(){

alert("Pedido realizado com sucesso!");

localStorage.removeItem("carrinho");

window.location.href="index.html";

}
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Painel Administrativo</title>

<link rel="stylesheet" href="css/style.css">

<style>
.container{
max-width:900px;
margin:40px auto;
padding:30px;
background:#fff;
border-radius:15px;
box-shadow:0 10px 30px rgba(0,0,0,.1);
}

input{
width:100%;
padding:15px;
margin:10px 0;
border-radius:8px;
border:1px solid #ddd;
}

button{
padding:15px;
width:100%;
background:#111;
color:white;
border:none;
border-radius:8px;
cursor:pointer;
}

.lista{
margin-top:30px;
}
</style>

</head>
<body>

<div class="container">

<h2>Cadastrar Produto</h2>

<input id="nome" placeholder="Nome do produto">

<input id="preco" placeholder="Preço">

<input id="imagem" placeholder="URL da imagem">

<button onclick="salvarProduto()">
Cadastrar Produto
</button>

<div class="lista" id="lista"></div>

</div>

<script src="js/admin.js"></script>

</body>
</html>let produtos = JSON.parse(localStorage.getItem("produtos")) || [];

function salvarProduto(){

const produto = {

nome:document.getElementById("nome").value,

preco:document.getElementById("preco").value,

imagem:document.getElementById("imagem").value

};

produtos.push(produto);

localStorage.setItem("produtos",JSON.stringify(produtos));

mostrarProdutos();

}

function mostrarProdutos(){

const lista=document.getElementById("lista");

lista.innerHTML="";

produtos.forEach(p=>{

lista.innerHTML+=`

<div class="card">

<img src="${p.imagem}" width="120">

<h3>${p.nome}</h3>

<p>R$ ${p.preco}</p>

</div>

`;

});

}

mostrarProdutos();const produtos = JSON.parse(localStorage.getItem("produtos")) || [
{
id:1,
nome:"Smartwatch Ultra",
preco:199.90,
imagem:"https://picsum.photos/400/400?1"
},
{
id:2,
nome:"Fone Bluetooth",
preco:89.90,
imagem:"https://picsum.photos/400/400?2"
},
{
id:3,
nome:"Mini Projetor",
preco:399.90,
imagem:"https://picsum.photos/400/400?3"
},
{
id:4,
nome:"Caixa de Som Bluetooth",
preco:149.90,
imagem:"https://picsum.photos/400/400?4"
}
];

const grid = document.querySelector(".grid");

if(grid){

grid.innerHTML="";

produtos.forEach(produto=>{

grid.innerHTML+=`

<div class="card">

<img src="${produto.imagem}" alt="${produto.nome}">

<h3>${produto.nome}</h3>

<p>R$ ${produto.preco.toFixed(2).replace(".",",")}</p>

<button onclick="comprar(${produto.id})">

Adicionar ao Carrinho

</button>

</div>

`;

});

}

function comprar(id){

const produto=produtos.find(p=>p.id==id);

let carrinho=JSON.parse(localStorage.getItem("carrinho"))||[];

carrinho.push(produto);

localStorage.setItem("carrinho",JSON.stringify(carrinho));

alert("Produto adicionado ao carrinho!");

}<script src="js/produtos.js"></script>
<script src="js/script.js"></script>
