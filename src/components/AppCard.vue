<script>

export default {
    name: 'AppCard',
    data() {
        return {
            products: [
                {
                    hideImage: '/img/1b.webp',
                    image: '/img/1.webp',
                    brand: "Levi's",
                    name: 'Relaxed fit tee unisex',
                    price: 14.99,
                    oldPrice: 29.99,
                    discount: 50,
                    sustainability: true
                },
                {
                    hideImage: '/img/2b.webp',
                    image: '/img/2.webp',
                    brand: 'Guess',
                    name: 'Roses tee',
                    price: 20.99,
                    oldPrice: 29.99,
                    discount: 30,
                    sustainability: false
                },
                {
                    hideImage: '/img/3b.webp',
                    image: '/img/3.webp',
                    brand: 'Come Zucchero Filato',
                    name: 'Voglia di colori pastello',
                    price: 129.99,
                    oldPrice: 29.99,
                    discount: 30,
                    sustainability: false
                },
                {
                    hideImage: '/img/4b.webp',
                    image: '/img/4.webp',
                    brand: "Levi's",
                    name: 'tee unisex',
                    price: 14.99,
                    oldPrice: 29.99,
                    discount: 50,
                    sustainability: true
                },
                {
                    hideImage: '/img/5b.webp',
                    image: '/img/5.webp',
                    brand: 'Maya Deluxe',
                    name: 'Stripe Bodice',
                    price: 99.99,
                    oldPrice: null,
                    discount: null,
                    sustainability: false
                },
                {
                    hideImage: '/img/6b.webp',
                    image: '/img/6.webp',
                    brand: 'Esprit',
                    name: 'Maglione - Black',
                    price: 29.99,
                    oldPrice: null,
                    discount: null,
                    sustainability: true
                }
            ]
        }
    }
}
</script>



<template>
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
</template>


<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as vars;
@use '../assets/styles/partials/mixin' as mixin;

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
</style>