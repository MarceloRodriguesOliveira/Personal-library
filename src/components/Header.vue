<template>
  <div>
    <nav id="nav">
      <h1><a href="/"><span>My</span> Library.</a></h1>
      <div id="views">
        <router-link to="/" class="nav-views">Home</router-link>
        <router-link to="/register" class="nav-views">Register</router-link>
    </div>
    </nav>
    
  </div>
</template>

<script>
export default {
  name: "Header"
}
</script>


<style scoped>
  *{
    text-decoration: none;
    background-color: #1c232d;
  }
  #nav{
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    height: 10vh;
    min-width: 280px;
   
  }

  #nav h1 a{
    padding-left: 10px;
    color: hsl(193, 38%, 86%); 
    
  }
  
  #nav h1 span{
    color: hsl(150, 74%, 41%);
    

  }

  #views{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
  }

  #views .nav-views{
    color: hsl(193, 38%, 86%);
    padding: 0px 10px;
    transition: .2s ease-out;
  }

  #views .nav-views:hover{
    color: hsl(150, 74%, 41%);

  }
</style>