<script setup>
defineProps({
    nome: "",
    
})
</script>

<template>
      <div>
          <div>
              <span class="titulo">Nome</span>
              <span class="conteudo">{{ nome }}</span>
          </div>
          <div>
              <span class="titulo">Height</span>
              <span class="conteudo">{{ height }}</span>
           </div>
           <div>
               <span class="titulo">Mass</span>
               <span class="conteudo">{{ mass }}</span>
           </div>
            <h3>Movimentos</h3>
                     
        </div> 
    <main>
        <TheWelcome />
    </main>
</template>

<style scoped></style>