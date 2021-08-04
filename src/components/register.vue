<template>
    <div>
        <h2 class="btn btn-warning text-muted p-5" >{{msg}}</h2>
    </div>
</template>


<script>
export default {
    name: 'register',
    data() {
        return {
            msg: ''
        }
    },
    }
</script>

<style scoped>
    h2{
        color: red ;
    }
</style>