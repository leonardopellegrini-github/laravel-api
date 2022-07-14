<template>


   <div class="container">
    
        <div v-for="post in posts" :key="post.id">
           <div class="card">
           <h3>Titolo post: {{post.title}}</h3>
           <p>Messaggio:</b> {{post.content}}</p>
           <p></p><span v-if="post.category"><b>Categoria:</b> {{post.category.name}}</span></p>
           </div>
        </div>
    </div>


</template>

<script>
export default {
    name: 'App',

   data() {
        return {
            apiUrl: "http://127.0.0.1:8000/api/posts",
            posts: []
        }
    },
    methods: {
        getApi() {
            axios.get(this.apiUrl).then((r) => {
                this.posts = r.data;
                console.log(r.data)
            });
        },
    },
    mounted() {
        this.getApi();
    }
}

</script>

<style>

</style>