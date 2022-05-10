<template>
    <div>
        <h1>Hello {{ get_user.name }}, What is up?</h1>
        <p>Email: {{ get_user.email }}</p>

    </div>
</template>


<script>
export default {
    data(){
        return {
            get_user : []
        };
    },
    created(){
        fetch(`https://jsonplaceholder.typicode.com/users/${this.$route.params.id}`)
        .then(response => response.json())
        .then(json => {
            this.get_user = json;
        });
    }
};
</script>