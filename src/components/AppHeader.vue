<script>

export default {
    name: 'Header',
    data() {
        return {
            link: [
                {
                    target: 'Donna',
                    link: ''
                },
                {
                    target: 'Uomo',
                    link: ''

                },
                {
                    target: 'Bambini',
                    link: ''
                }
            ],
            index: 0,
        }
    }
}

</script>

<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-25">
                    <span>
                        <ul class="unstyled-list text-center row space-around">
                            <li v-for="(target, index) in link"><a href="">{{ target.target }}</a></li>
                        </ul>
                    </span>
                </div>
                <div class="col-50 text-center py-5">
                    <img src="/img/boolean-logo.png" alt="Boolean logo" class="logo">
                </div>
                <div class="col-25 ">
                    <ul class="unstyled-list d-flex j-end">
                        <li><a href=""><img src="/img/user-svgrepo-com.svg" alt="user icon" class="icon"></a></li>
                        <li><a href=""><img src="/img/heart-svgrepo-com.svg" alt="heart icon" class="icon"></a></li>
                        <li><a href=""><img src="/img/bag-4-svgrepo-com.svg" alt="bag icon" class="icon"></a></li>
                    </ul>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as vars;
@use '../assets/styles/partials/mixin' as mixin;


header {
    background-color: vars.$bg_navBar;
    width: 100%;
    position: fixed;
    z-index: 100;

    .container {
        max-width: 1200px;
        margin: 30px auto;

        .row {
            @include mixin.flex-wrap;
        }
    }

    .col-25 {
        width: vars.$col-25;
        padding: 0 1rem;

        .unstyled-list {
            list-style: vars.$unstyled-list;
            padding: 0;
            margin: 0;
            display: flex;
        }

        .space-around {
            justify-content: space-around;
        }

        a {
            text-decoration: none;
            color: vars.$white_text
        }

        .d-flex {
            display: flex;
        }

        .j-end {
            justify-content: flex-end;
        }

    }

    .col-50 {
        width: vars.$col-50;

        .logo {
            width: 100px;
            height: auto;
        }

        .py-5 {
            padding: vars.$py-5 ;
        }
    }

    .text-center {
        text-align: center;
    }

    .icon {
        @include mixin.icon
    }
}
</style>

