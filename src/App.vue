<script setup>
import { computed, ref } from "vue";
const carrinho = ref(false);
const produtos = ref([
  {
    id: 1,
    titulo: 'Chain of Iron: Volume 2',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 23.24,
    capa: '/public/97819821858242.png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 2,
    titulo: 'Chain of Thorns',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 23.24,
    capa: '/public/97819821858242(1).png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 3,
    titulo: 'City of Fallen Angels',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 13.94,
    capa: '/public/97819821858242(2).png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 4,
    titulo: 'Nona the Ninth',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 16.84,
    capa: '/public/97819821858242(3).png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 5,
    titulo: 'Harlem Shuffle',
    autor: 'Colson Whitehead',
    booleano: false,
    preco: 26.92,
    capa: '/public/97819821858242(4).png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 6,
    titulo: 'Two Old Women',
    autor: 'Velma Wallis',
    booleano: false,
    preco: 13.95,
    capa: '/public/97819821858242(5).png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 7,
    titulo: 'Carrie Soto Is Back',
    autor: 'Taylor Jenkins Reid',
    booleano: false,
    preco: 26.04,
    capa: '/public/97819821858242(6).png',
    quantidade: 1,
    favoritar: false,
  },
  {
    id: 8,
    titulo: 'Book Lovers',
    autor: 'Emily Henry',
    booleano: false,
    preco: 15.81,
    capa: '/public/97819821858242(7).png',
    quantidade: 1,
    favoritar: false,
  },



]);
const total = computed(() => {
  let total = 0;
  for (let item of produtos.value) {
    if (item.booleano == true) {
      total += item.preco * item.quantidade;
    }
  }
  return total.toFixed(2)
});


function aumentarquantidade(livro) {
  livro.quantidade++;
}

function diminuirquantidade(livro) {
  if (livro.quantidade > 1) {
    livro.quantidade--;
  }
}


for (let items of produtos.value) {
  if (items.booleano == false) {
    items.quantidade == 1
  }
}
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
              <p>{{ book.preco }} <span @click="book.favoritar = !book.favoritar"
                  :class="book.favoritar ? 'fa-solid fa-heart' : 'fa-regular fa-heart'"></span></p>
              <button @click="book.booleano = !book.booleano; book.quantidade = 1"><span
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
              <button class="lixeira" @click="livro.booleano = !livro.booleano; livro.quantidade = 1"><span
                  class="fa-solid fa-trash"></span></button>
            </div>
          </div>
        </div>
        <div class="voltar">
          <button @click="carrinho = !carrinho">Voltar para loja</button>
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
      <p class="copy">&copy; Alguns direitos reservados. IFbooks 2025.</p>
    </footer>
  </body>
</template>

<style scoped>
header {
  border-bottom: #27AE60 solid 2px;
  padding: 1vw 15vw 0vw 15vw;
}

a {
  text-decoration: none;
}

body {
  overflow-x: hidden;
  margin: 0;
  background-color: #FFFFFF;
}

/*=============================================
                    Header
===============================================*/
header nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-bottom: 10px;
}

header nav div:first-child {
  display: flex;
  align-items: center;
}

header nav div:first-child a {
  color: black;
  font-size: 20px;
}

header nav div:first-child hr {
  margin: 0 10px;
  height: 30px;
  border-color: #27AE60;
}

header nav div:first-child p {
  color: #27AE60;
  font-size: 13px;
  width: 30%;
}




div.input {
  display: flex;
  align-items: center;
  position: relative;
}

.input input {
  width: 376px;
  height: 36px;
  padding-right: 35px;
  padding: 0 0 0 10px;
  background-color: #F1F1F1;
  color: #B8B8B8;
  border: none;
  border-radius: 5px;

}

.input span {
  position: absolute;
  color: #B8B8B8;
  right: 10px;
}



.ul ul {
  display: flex;
  list-style: none;
  gap: 30px;
}

.ul ul li a {
  color: #7B7881;
  font-size: 14px;
}


.icons {
  display: flex;
  align-items: center;
  gap: 15px;
}

.icons a {
  color: #7B7881;
  font-size: 18px;
}

.icons span {
  color: #27AE60;
}

.icons hr {
  height: 20px;
  width: 1px;
  background-color: #ccc;
  border: none;
}

/*=============================================
                    Main
===============================================*/
main {
  margin: 0vw 15vw;
}

section.primeira {
  display: flex;
  border-bottom: #27AE60 solid 2px;
  margin: 0 0 2.5vw 0;
}

section.primeira div:first-child {
  margin: 2vw 0;
}

section.primeira div p:first-child {
  padding: 10px;
  border: 1px solid #27AE60;
  width: 16%;
  font-size: 14px;
  text-align: center;
  color: #27AE60;
}

section.primeira div h1 {
  font-size: 48px;
  font-weight: bold;
  color: #382C2C;
}

section.primeira div p:not(p:first-child) {
  color: #4D4C4C;
  font-size: 16px;
  line-height: 22px;
  margin-bottom: 2vw;
  width: 40%;
}

section.primeira div button {
  padding: 15px 30px;
  font-size: 16px;
  background-color: #27AE60;
  border: none;
  color: #FFFFFF;
}


section.primeira div p:last-child {
  position: relative;
  margin-left: 12vw;
  top: -3.5vw;
}

/*=============================================
                    Main - Parte 2
===============================================*/

.segunda {
  display: flex;
  justify-content: space-between;
  padding-bottom: 2.5vw;
  border-bottom: #27AE60 2px solid;
}

.segunda div {
  display: flex;
  align-items: center;
  gap: 15px;
}

.segunda div span {
  font-size: 28px;
  color: #382C2C;
}

.segunda div p {
  font-size: 22px;
  color: #382C2C;
}

.segunda div hr {
  width: 10px;
}

.maisV {
  position: relative;
}

.segunda div:last-child p:last-of-type {
  position: absolute;
  right: 14vw;
  padding-top: 10px;
}

/*=============================================
                    Main - Parte 3
===============================================*/
.four {
  justify-content: space-between;
  display: flex;
  flex-wrap: wrap;
}

.terceiro {
  margin-bottom: 10vw;
}

.terceiro h2 {
  font-size: 38px;
  font-weight: bolder;
  padding: 2vw 0 1vw 0;
}

.four div h3 {
  font-size: 24px;
  font-weight: bold;
  color: #382C2C;
  margin-top: 22px;
  margin-bottom: 0;
}

.four div p {
  color: #4F4C57;
  margin-top: 10px;
}

.four div p:last-of-type {
  color: #382C2C;
  font-weight: bold;
  font-size: 20px;
  margin-bottom: 1.9vw;
}

.four div p:last-of-type span {
  margin-left: 9vw;
  color: #27AE60;

}
.four div p:last-of-type span:hover{
  cursor: pointer;
}


.four div button {
  color: #FFFFFF;
  background-color: #27AE60;
  width: 100%;
  height: 48px;
  font-size: 16px;
  border: none;
  margin-bottom: 5vw;
}
.four div button:hover{
  cursor: pointer;
}

.four div button span {
  padding-right: 10px;
}






/*=============================================
                    Carrinho
===============================================*/



.principal-carrinho h1 {
  margin-top: 8vw;
  margin-bottom: 4vw;
  font-size: 38px;
  color: #27AE60;
}

.principal-carrinho ul {
  display: flex;
  padding: 0;
  justify-content: space-between;
  list-style: none;
}

.principal-carrinho li h2:first-of-type {
  padding-left: 10px;
}

.principal-carrinho h2 {
  font-size: 24px;
  color: #382C2C;
  margin: 0;
}

.meio {
  padding-left: 10vw;
}

.principal-carrinho hr {
  height: 1px;
  border: none;
  background-color: #27AE60;
  width: 69.46vw;
  position: relative;
  margin: 1vw 0 2vw 0;
}


.livros,
.botao {
  display: flex;
}

.livros {
  position: relative;
  border-bottom: gray solid 1px;
  margin-bottom: 2vw;
}

.livros .lixeira {
  position: absolute;
  border: none;
  background-color: #FFFFFF;
  font-size: 20px;
  left: 70vw;
  top: 2.3vw;
}

.separar {
  display: flex;
  width: 100%;
  justify-content: space-between;
}

.img img {
  width: 94px;
  height: 142px;
  margin: 0 2vw 2vw 0;
}

.infos {
  width: 248.5px;
}

.infos h2 {
  margin: 0;
  font-size: 24px;
  color: #382C2C;
}

.infos p:first-of-type {
  color: #4F4C57;
  font-size: 16px;
}

.infos p:last-of-type {
  color: #382C2C;
  font-size: 20px;
}

.botao {
  margin: 2vw 6vw 2vw 0.5vw;
  align-items: center;
  border: solid 1px black;
  padding: 0;
  height: 56px;
  width: 124px;
  justify-content: center;
  font-size: 20px;

}

.botao button {
  border: none;
  font-size: 20px;
}

.botao p {
  width: 40px;
  color: black;
  text-align: center;
}

.valor p {
  padding: 35px 0 0 5px;
  font-size: 24px;
  width: 100px;
  text-align: center;
  color: #382C2C;
}

.voltar button {
  padding: 10px 40px;
  font-size: 16px;
  background-color: #FFFFFF;
  border: 1px solid gray;
  border-radius: 3px;
  margin-bottom: 5vw;
}



.finalizacao {
  display: flex;
  justify-content: space-between;
}

.finalizacao input {
  padding: 15px 0 15px 10px;
  padding-right: 40px;
  border: 1px solid black;
  border-radius: 3px;
}

.finalizacao button {
  padding: 15px 30px;
  margin-left: 10px;
  border-radius: 3px;
  border: none;
  background-color: #27AE60;
  color: #FFFFFF;
}



.compra {
  border: solid 1px black;
  padding: 5px 20px 25px 20px;
  width: 350px;
  margin-bottom: 8vw;
}

.compra h3 {
  color: black;
  font-size: 20px;
}

.compra ul li {
  display: flex;
  justify-content: space-between;
  color: black;
  margin: 0.5vw 0 0.5vw 0;
}

.compra ul {
  padding: 0;
}

.compra .btn {
  text-align: center;

}









/*=============================================
                    Footer
===============================================*/
footer {
  background-color: #27AE60;
  padding: 30px 0 1px 0;
}

footer nav {
  display: flex;
  justify-content: space-between;
  padding: 1vw 10vw;
}

footer ul {
  margin: 0;
  padding: 0;
}

footer div:first-of-type h4 {
  font-size: 16px;
  color: #FFFFFF;
  margin-bottom: 15px;
}

footer div:first-of-type ul,
.contact ul {
  display: flex;
  list-style: none;
  gap: 15px;
}

.contact ul {
  margin: 50px 0 25px 0;
}
.contact {
  color: #FFFFFF;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.contact h4 {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 10px;
}
.contact span {
  padding-right: 5px;
}

.copy {
  text-align: center;
  color: #FFFFFF;
  padding: 10px 0;
}

</style>
