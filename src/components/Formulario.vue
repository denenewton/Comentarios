<template>
 
 <div class="container">
       <h1>Comentários</h1>
       <div class="form-todo form-group mt-4">
       <p><input v-model="name" type="text" name="author" placeholder="nome" class="form-control"></p>
       <p><textarea v-model="message"  name="message"  rows="5" placeholder="comentário" class="form-control"></textarea></p>
       <button v-on:click="addCommets" type="submit" class="btn btn-primary">comentar</button>
      </div>
 </div>

</template>

<script>

export default {
    
    data(){
        return{
           name: '', 
           message: '',
           id: 0
        }
    },
    props:{

    },

    methods: {
        addCommets(){
                   
                   if(this.name.trim() === " " || this.message.trim() ===''){
                    return;
                   }else{
 
                        this.$emit('add-coments', {// emitindo um evento que passa os campos que ira popular o comentario.
          
                        id: this.id ++,
                        nome: this.name,
                        mensagem: this.message
                       
                        })

                       this.name = ''   
                       this.message = ''

                   }
                   

                  
               }

    }

}
</script>

<style>

</style>