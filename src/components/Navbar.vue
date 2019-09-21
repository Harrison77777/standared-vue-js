<template>
    <nav class="navbar navbar-expand-lg navbar-light  bg-info">
        <a class="navbar-brand" href="#">Cart System</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item active">
                    <a class="nav-link " href="#">Home <span class="sr-only">(current)</span></a>
                </li>
            </ul>
            <form @submit.prevent="searchFormSubmit" class="form-inline my-2 my-lg-0">
                <input v-model="keyword" class="form-control form-control-sm mr-sm-2" type="search" placeholder="Search"
                    aria-label="Search">
                <button  class="btn btn-sm btn-success my-2 my-sm-0" type="submit">Search</button>
            </form>
        </div>
    </nav>
</template>
<script>
    export default {
        data(){
            return {
                keyword: ''
            }
        },
        methods:{
            searchFormSubmit(){
                this.$emit('searchResult', this.keyword)
            }
        }
    }
</script>
<style>

</style>