<template>
    <div id="form-container">
        <div id="input_title" class="input_config">
            <input type="text" name="title_txt" id="title_txt" v-model="title" placeholder="Insert Book Title">
        </div>
        <div id="input_author" class="input_config">
            <input type="text" name="author_txt" id="author_txt" v-model="author" placeholder="Insert Author">
        </div>
        <div id="input_code" class="input_config">
            <input type="text" name="ol_id" id="ol_id" v-model="idCode" placeholder="ISBN ">
        </div>
        <button id="btn_send" @click="createBooks">REGISTER</button>
    </div>
</template>


<script>
export default {
    name: "RegisterForm",
    data(){
        return{
            title:null,
            author:null,
            idCode:null,
            linkurl:null
        }
    },
    methods:{
        async createBooks(){

            const imgurl = await fetch(`https://covers.openlibrary.org/b/isbn/${this.idCode}-M.jpg`)
            this.linkurl = imgurl.url
            
            const data={
                title:this.title,
                author:this.author,
                oplid:this.idCode,
                coversource:this.linkurl
            }

            

            const dataJson = JSON.stringify(data)

            //Postando o livro
            const req =  await fetch("http://localhost:3000/Books",{
                method:"POST",
                headers: {"Content-Type":"application/json"},
                body: dataJson
            })

            // console.log(res)

            
        }
    }
}
</script>

<style scoped>
    *{
        color: white;
    }

    #form-container{
        min-height: 85vh;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;   
         
    }


    #btn_send{
        margin-top: 50px;
        width: 16.75rem;
        height: 2.5rem;
        border-radius: 20px;
        border: 3px solid hsl(150, 74%, 41%);
        background-color: #1c232d;
        letter-spacing: 3px;
        cursor: pointer;
        transition: .2s;
    }

    #btn_send:hover{
       color: hsl(151, 87%, 55%);
       background-color: #4a5058;
    }

    .input_config{
        margin-top: 40px;
    }

    .input_config input[type=text]{
        width: 18.75rem;
        height: 2.5rem;
        border-radius: 8px;
        padding-left: 5px;
        background-color: #1c232d;
        border: 3px solid hsl(150, 74%, 41%);
    }



  



</style>