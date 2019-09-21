<template>
    <div class="col-md-8">
        <div class="card-section">
            <div class="row">
                <div v-for="(item, index) in items" :key="index" class="col-lg-4 col-md-6 mb-4">
                    <div class="card h-100">
                        <img class="card-img-top" :src="item.photo" alt="">
                        <div class="card-body">
                            <h5 class="card-title">{{item.name}}</h5>
                            <p class="card-text">Price : {{item.price}}$</p>
                        </div>
                        <div class="card-footer text-center">
                            <a @click.prevent="addToCart(item)" href="#" class="btn btn-sm btn-primary">Add To Cart</a>
                        </div>
                    </div>
                </div>
                
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props:['items'],
        methods:{
          addToCart(item){
              this.$emit('addedNewItem', item)
          }  
        }
    }
</script>
<style>

</style>