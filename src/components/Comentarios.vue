<template>
  <div class="Comentarios">
    <Formulario  v-on:add-coments="addComents"/>
    <div class="container">
      <hr>
      <div class="alert alert-danger" role="alert" v-if='commets.length < 1'>
         Nenhum comentario no memento!
      </div>
      <div v-else class="list-group" v-for="(commet, index) in allComents" :key="index">
       <div class="list-group-item mt-3">
         <span class="comment__author">Autor: <strong>{{commet.nome}}</strong>  </span>
         <p>{{commet.mensagem}}</p>
         <p><a href="" class="" v-on:click.prevent="delComment(index)">Deletar</a></p>
       </div>
     </div>
    </div>
  </div>   
</template>  
<!------- -------------------->
<script>
import Formulario from './Formulario'

export default {

    components:{
      Formulario
    },

    data(){
        return {
           commets: [ ],// lista de comentários...
                 
        }                                        
    },
    props: {
    coments: Array
    },

    methods: {
               
               delComment: function(index){
                 console.log(index)
                    this.commets.splice(index, 1)
                    
        },
        addComents: function(commet){
           this.commets.push(commet)
        }

    }, 
    computed: {
      allComents: function(){
        return this.commets.map( commet => ({
          ...commet,
             nome: commet.nome.trim() ==='' ? 'Anônimo': commet.nome
        })).reverse()
      }
    },
   watch: {
     commets(val){
       console.log('val', val)
     }
   }  

    
    
}

</script>

