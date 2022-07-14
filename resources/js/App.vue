<template>


  <h1>Questo è App</h1>

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