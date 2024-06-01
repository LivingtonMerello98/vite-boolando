<script>
import ProductsData from '../assets/data/db.json'
export default {
    name: 'Main',
    data() {
        return {
            products: ProductsData,
        }
    }
}
</script>


<template>
    <main class="py-120">
        <div class="container">
            <div class="row">
                <div class="col-33" v-for="(product, index) in products" :key="index">
                    <div class="content">
                        <img :src="product.hideImage" :alt="'hide ' + product.name" class="hide img">
                        <img :src="product.image" :alt="product.name">
                        <div class="bg-white pxy-10-20">
                            <span class="red-heart-label bg-white">&hearts;</span>
                            <span class="heart-label bg-white">&hearts;</span>
                        </div>
                        <div v-if="product.discount" class="discount-label bg-red white z-index-3">
                            <span>&#45;{{ product.discount }}&#37;</span>
                        </div>
                        <div v-if="product.sustainability" class="sustainability-label bg-green white z-index-3">
                            <span>Sostenibilità</span>
                        </div>
                    </div>
                    <span class="brand">{{ product.brand }}</span>
                    <h4 class="dress-name">{{ product.name }}</h4>
                    <span class="product-price">{{ product.price }}&euro;</span>
                    <span v-if="product.oldPrice" class="old-price">{{ product.oldPrice }}&euro;</span>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as vars;
@use '../assets/styles/partials/mixin' as mixin;
@use '../style.scss' as style;

main {
    padding-top: 120px;

    .container {
        max-width: 1200px;
        margin: 30px auto;

        .row {
            @include mixin.flex-wrap;

            .col-33 {
                @include mixin.col-33;

                .content {
                    position: relative;

                    img {
                        width: 100%;
                        height: auto;
                    }

                    .hide {
                        @include mixin.hide;
                    }

                    .content:hover .hide {
                        display: block;
                        z-index: 2;
                    }

                    .bg-white {
                        background-color: vars.$bg_background;
                    }

                    .pxy-10-20 {
                        padding: vars.$pxy-10-20;

                        .red-heart-label {
                            position: absolute;
                            color: red;
                            font-size: 30px;
                            top: 10px;
                            right: 0;
                            padding: 10px 20px;
                            opacity: 0;
                            z-index: 3;

                        }

                        .heart-label {
                            position: absolute;
                            font-size: 30px;
                            top: 10px;
                            right: 0;
                            padding: 10px 20px;
                            z-index: 2;
                        }

                        .bg-white:hover.red-heart-label {
                            opacity: 1;
                        }
                    }

                    .discount-label {
                        position: absolute;
                        bottom: 80px;
                        left: 0;
                        padding: 5px 10px;
                        z-index: 99;
                        background-color: vars.$bg_discount;
                        color: vars.$white_text
                    }

                    .sustainability-label {
                        position: absolute;
                        bottom: 80px;
                        left: 60px;
                        padding: 5px 10px;
                        z-index: 99;
                        background-color: vars.$bg_sustainability;
                        color: vars.$white_text
                    }

                }

                .brand {
                    font-size: vars.$font14;
                    font-weight: 300;
                }

                .dress-name {
                    text-transform: uppercase;
                }

                .product-price {
                    color: red;
                    font-size: 14px;
                    font-weight: 500;
                }

                .old-price {
                    font-size: 14px;
                    font-weight: 300;
                    text-decoration: line-through;
                    padding-left: 10px;
                }
            }
        }
    }

}
</style>