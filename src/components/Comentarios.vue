<template>
    <div class="Comentarios">
    
    <div class="container">
       <h1>Comentários</h1>
       <div class="form-todo form-group">
      
       <p><input v-model="name" type="text" name="author" placeholder="nome" class="form-control"></p>
     <p><textarea v-model="message"  name="message"  rows="5" placeholder="comentário" class="form-control"></textarea></p>
      <button v-on:click="addCommets" type="submit" class="btn btn-primary">comentar</button>
     <div class="list-group" v-for="(commet, index) in allComents" :key="index">
       <div class="list-group-item mt-3">
         <span class="comment__author">Autor: <strong>{{commet.nome}}</strong>  </span>
         <p>{{commet.mensagem}}</p>
         <p><a href="" class="" v-on:click.prevent="delComment(index)">Deletar</a></p>
       </div>

     </div>
    </div>
    </div>
    </div>   
</template>
     

   

<script>
export default {
    
    data(){
        return {
           commets: [ ],// lista de comentários...
           name: '', 
           message: '',
           id: 0
                
    
        }                               
           
    },
    props: {
    coments: Array
    },

    methods: {
               addCommets(){
                   
                   if(this.name.trim() === " " || this.message.trim() ===''){
                    return;
                   }else{
                      this.commets.push(
                       {
                       id: this.id ++,
                       nome: this.name,
                       mensagem: this.message
                       } )

                  //  console.log(this.name)
                   // console.log(this.message)
                    //console.log(this.id)   

                    this.name = ''   
                    this.message = ''

                   }
                   

                  
               },
               delComment: function(index){
                 console.log(index)
                    this.commets.splice(index, 1)
                    
               }


    }, 
    computed: {
      allComents: function(){
        return this.commets.map( commet => ({
          ...commet,
             nome: commet.nome.trim() ==='' ? 'Anônimo': commet.nome
        }))
      }
    },
   watch: {
     commets(val){
       console.log('val', val)
     }
   }  

    
    
}

</script>

