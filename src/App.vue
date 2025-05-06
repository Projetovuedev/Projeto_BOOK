<script setup>

</script>

<template>
<body>

<header>
  <nav>
    <div>
      <a href="index.html">IFbooks</a>
      <hr>
      <p>Apreço a leitura</p>
    </div>
    <div class="input">
      <input type="search" placeholder="Pesquisar...">
      <span class="fa-solid fa-magnifying-glass"></span>
    </div>
    <div class="ul">
      <ul>
        <li><a href="#">Termos</a></li>
        <li><a href="#">Equipe</a></li>
        <li><a href="#">Envio</a></li>
        <li><a href="#">Devoluções</a></li>
      </ul>
    </div>
    <div class="icons">
      <a href="#" @click="carrinho = !carrinho"><span class="fa-solid fa-cart-shopping"></span></a>
      <hr>
      <a href="#"><span class="fa-solid fa-heart"></span></a>
      <hr>
      <a href="#"><span class="fa-solid fa-user"></span></a>
    </div>
  </nav>
</header>


<main>
  <div v-if="carrinho === !true">
  <section class="primeira">
    <div>
      <p>Autor de Abril</p>
      <h1>Eric-Emanuel Schmitt </h1>
      <p>Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and in 2001
        he
        received the title of Chevalier des Arts et des Lettres. His books have been translated into
        over 40
        languages.</p>
      <button>Acessar página do livro</button>
    </div>
    <div>
      <img src="/public/book.png" alt="Livro 1">
      <p>*within the stock limit</p>
    </div>
  </section>


  <section class="segunda">
    <div>
      <span class="fa-solid fa-truck"></span>
      <p>Frete grátis para SC</p>
    </div>
    <hr>
    <div>
      <span class="fa-solid fa-star"></span>
      <p>Livros recomendados</p>
    </div>
    <hr>
    <div>
      <span class="fa-solid fa-book-open"></span>
      <p class="maisV">Mais vendidos</p>
      <p>______________</p>
    </div>
  </section>
  <section class="terceiro">
    <h2>Lançamentos</h2>

    <div class="four">
      <div v-for="book in produtos" :key="book.id">
        <img :src="book.capa" :alt="book.titulo">
        <h3>{{ book.titulo }}</h3>
        <p>{{ book.autor }}</p>
        <p>{{ book.preco }} <span @click="favoritar"></span></p>
        <button @click="book.booleano = !book.booleano"><span
            class="fa-solid fa-cart-shopping"></span>Comprar</button>
      </div>
    </div>

  </section>
  </div>
  <section class="carrinho" v-if="carrinho">
    <div class="principal-carrinho">
      <h1>Carrinho</h1>
      <ul>
        <li>
          <h2>Título</h2>
        </li>
        <li class="meio">
          <h2>Quantidade</h2>
        </li>
        <li>
          <h2>Subtotal</h2>
        </li>
      </ul>
      <hr>
    </div>
    <div v-for="livro in produtos" :key="livro.id">
      <div v-if="livro.booleano" class="livros">
        <div class="img">
          <img :src="livro.capa" :alt="livro.titulo">
        </div>
        <div class="separar">
          <div class="infos">
            <h2>{{ livro.titulo }}</h2>
            <p>{{ livro.autor }}</p>
            <p>R$ {{ livro.preco }}</p>
          </div>
          <div class="botao">
            <button @click="diminuirquantidade(livro)">-</button>
            <p>{{ livro.quantidade }}</p>
            <button @click="aumentarquantidade(livro)">+</button>

          </div>
          <div class="valor">
            <p>{{ (livro.preco * livro.quantidade).toFixed(2).replace(".", ",") }}</p>
          </div>
          <div v-if="false">{{ produtoTotal(livro.preco) }}</div>
          <button class="lixeira" @click="livro.booleano = !livro.booleano ; livro.quantidade = 1"><span class="fa-solid fa-trash"></span></button>
        </div>
      </div>
    </div>
    <div class="voltar">
      <a href="index.html"><button>Voltar para loja</button></a>
    </div>
    <section class="finalizacao">
      <div>
        <input type="text" placeholder="Código do Cupom">
        <button>Inserir Cupom</button>
      </div>
      <div class="compra">
        <h3>Total da Compra</h3>
        <ul>
          <li>
            <p>Produtos:</p>
            <p>{{ total }}</p>
          </li>
          <hr>
          <li>
            <p>Frete:</p>
            <p>Grátis</p>
          </li>
          <hr>
          <li>
            <p>Total:</p>
            <p>{{ total }}</p>
          </li>
        </ul>
        <div class="btn">
          <button>Ir para o pagamento</button>
        </div>
      </div>
    </section>
  </section>
</main>
<footer>
  <nav>
    <div>
      <h4>IFbooks</h4>
      <ul>
        <li><a href="#"><img src="/public/facebook.png" alt="Facebook"></a></li>
        <li><a href="#"><img src="/public/instagram.png" alt="Instagram"></a></li>
        <li><a href="#"><img src="/public/twitter.png" alt="Twitte"></a></li>
      </ul>
    </div>
    <div class="contact">
      <h4>Contatos</h4>
      <p><span class="fa-solid fa-phone"></span> +55 47 40045263</p>
      <p><span class="fa-solid fa-clock"></span> 8h às 23h - Seg a Sex</p>
      <p><span class="fa-solid fa-envelope"></span> contato@ifbooks.com</p>
      <ul>
        <li><img src="/public/paipal 1.png" alt="PayPal"></li>
        <li><img src="/public/MasterCard-Logo-1979 1.png" alt="MasterCard"></li>
        <li><img src="/public/VISA-card-logo- 1.png" alt="VisaCard"></li>
      </ul>
    </div>
  </nav>
  <hr>
  <p>&copy; Alguns direitos reservados. IFbooks 2025.</p>
</footer>
</body>
</template>

<style scoped>

</style>
