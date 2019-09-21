<template lang="">
    <div class="col-md-4">
        <div class="cart-section">
            <div class="col-md-12">
                <ul class="list-group">
                    <li class="list-group-item mb-2 bg-light">Cart Product List</li>
                    <li v-for="(item, index) in items" :key="index" class="list-group-item">
                        <div class="row  no-gutters">
                            <div class="col-md-7">{{item.name}}</div>
                            <div class="col-md-2 text-left">
                                <img class="rounded" height="30" :src="item.photo" alt="">
                            </div>
                            <div class="col-md-2">${{item.price}}</div>
                            <div class="col-md-1">
                                <div class="cart-remove-button">
                                    <button class="btn btn-sm btn-danger" @click="removeItem(index)" type="button">
                                        X
                                    </button>
                                </div>

                            </div>
                        </div>

                    </li>
                    <li class="list-group-item mt-2 text-light bg-secondary">
                        Total Price - ${{totalPrice}}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props: ['items'],
        computed: {
            totalPrice() {
                let totalPrice = 0
                this.items.forEach(item => {
                    totalPrice += parseFloat(item.price)
                })
                return totalPrice
            }
        },
        methods: {
            removeItem(index) {
                this.items.splice(index, 1)
            }
        },

    }
</script>
<style>

</style>