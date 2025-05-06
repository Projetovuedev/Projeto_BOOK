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
  },
  {
    id: 2,
    titulo: 'Chain of Thorns',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 23.24,
    capa: '/public/97819821858242(1).png',
    quantidade: 1,
  },
  {
    id: 3,
    titulo: 'City of Fallen Angels',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 13.94,
    capa: '/public/97819821858242(2).png',
    quantidade: 1,
  },
  {
    id: 4,
    titulo: 'Nona the Ninth',
    autor: 'Cassandra Clare',
    booleano: false,
    preco: 16.84,
    capa: '/public/97819821858242(3).png',
    quantidade: 1,
  },
  {
    id: 5,
    titulo: 'Harlem Shuffle',
    autor: 'Colson Whitehead',
    booleano: false,
    preco: 26.92,
    capa: '/public/97819821858242(4).png',
    quantidade: 1,
  },
  {
    id: 6,
    titulo: 'Two Old Women',
    autor: 'Velma Wallis',
    booleano: false,
    preco: 13.95,
    capa: '/public/97819821858242(5).png',
    quantidade: 1,
  },
  {
    id: 7,
    titulo: 'Carrie Soto Is Back',
    autor: 'Taylor Jenkins Reid',
    booleano: false,
    preco: 26.04,
    capa: '/public/97819821858242(6).png',
    quantidade: 1,
  },
  {
    id: 8,
    titulo: 'Book Lovers',
    autor: 'Emily Henry',
    booleano: false,
    preco: 15.81,
    capa: '/public/97819821858242(7).png',
    quantidade: 1,
  },



]);
function favoritar(){

}

const total = computed(() => {
  let total = 0;
  for(let item of produtos.value){
    if(item.booleano == true){
      total+= item.preco * item.quantidade;
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


for(let items of produtos.value){
  if(items.booleano == false){
    items.quantidade == 1
  }
}
</script>

<template>

</template>

<style scoped>

</style>
