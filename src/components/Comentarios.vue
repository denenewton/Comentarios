<template>
    <div class="Comentarios">
    
    <div class="container">
       <h1>Comentários</h1>
       <div class="form-todo form-group">
      
       <p><input v-model="name" type="text" name="author" placeholder="nome" class="form-control"></p>
     <p><textarea v-model="message"  name="message"  rows="5" placeholder="comentário" class="form-control"></textarea></p>
      <button v-on:click="addCommets" type="submit" class="btn btn-primary">comentar</button>
     <div class="list-group" v-for="commet in commets" :key="commet.id">
       <div class="list-group-item mt-3">
         <span class="comment__author">Autor: <strong>{{commet.nome}}</strong>  </span>
         <p>{{commet.mens}}</p>
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
           commets: [
               {   
                   id: 0,
                   nome: 'Daniel Santos Araujo',
                   mens: 'Gosto muito de aprender'
               }

            ],
           name: 'daniel', 
           message: 'fdsffsdfdsf',
           id: 1
                
    
        }                               
           
    },

    methods: {
               addCommets(){
                   console.log(this.name)
                   console.log(this.message)
                   console.log(this.id)
                   this.commets.push(
                       {
                       id: this.id ++,
                       nome: this.name,
                       mens: this.message
                       }
                   )

               }


    }      

    
    
}

</script>

