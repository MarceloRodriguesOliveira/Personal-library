<template>
  <div id="book-container">
    <h4>Currently Reading</h4>
    <div id="galeria">
      <div class="quadro" v-for="book in books" :key="book.id">
        <img :src="book.coversource" alt="book-cover">
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'HomeView',
  data(){
    return{
      books:null,
      
    }
  },
  methods:{
    async getBooks(){
      
      const req = await fetch("http://localhost:3000/Books")
      const data  = await req.json()

      this.books = [...data]
      console.log('atualizou') 

    }
  },
  mounted(){
    setInterval(() => {
      this.getBooks()
    }, 7000);
  }
}
</script>

<style scoped>
  #book-container{
    height: 100%;
    min-height: 85vh;
  }

  #book-container h4{
    color: hsl(193, 38%, 86%);
    border-bottom: 1px solid #1c232d;
    padding: 20px 0px 5px 10px;
    transition: .2s;
  }

  #book-container h4:hover{
    color: hsl(150, 74%, 41%);
  }

  #galeria{
    margin: 10px 20px;
    display: flex;
    flex-wrap: wrap;
    gap: 45px;
    
  }

  #galeria .quadro{
    margin: 10px 0;
    width: 180px;
    height: 269px;
    
    
    
  }

  .quadro img{
    border: 5px solid #1c232d;
    width: 180px;
    height: 269px;
    
  }

  @media(max-width:1089px){
    #galeria{
      justify-content: center;
    }
  }

</style>
