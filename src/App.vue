<script setup>

</script>

<template>

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

.four div button {
  color: #FFFFFF;
  background-color: #27AE60;
  width: 100%;
  height: 48px;
  font-size: 16px;
  border: none;
  margin-bottom: 5vw;
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
.livros .lixeira{
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
  padding-bottom: 1px;
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
}

footer div:first-of-type ul,
.contact ul {
  display: flex;
  list-style: none;
  gap: 15px;
}

.contact ul {
  margin: 50px 0;
}

.contact {
  color: #FFFFFF;
}

.contact h4 {
  font-size: 16px;
  font-weight: bold;
}

.contact span {
  padding-right: 5px;
}

footer p:last-of-type {
  text-align: center;
  color: #FFFFFF;
  padding: 10px 0;
}
</style>
