<script>
export default {
    name: 'Footer',
}
</script>

<template>
    <footer class="py-20">
        <div class="container">
            <div class="row">
                <div class="col-100">
                    <div class="d-flex space-between">
                        <div>
                            <h2 class="h2-footer white my-5">Boolando s.r.l</h2>
                            <span class="white f-w-300 f-s-14 ">informazioni legali informativa sulla privacy Diritto di
                                recesso</span>
                        </div>
                        <div class="text-left">
                            <span class="white f-w-500 f-s-14 my-10">trovaci anche su</span>
                            <ul class="unstyled-list d-flex j-start">
                                <li><a href=""><img src="/img/twitter-rounded-svgrepo-com.svg" alt="user icon"
                                            class="icon"></a></li>
                                <li><a href=""><img src="/img/facebook-svgrepo-com (1).svg" alt="heart icon"
                                            class="icon"></a></li>
                                <li><a href=""><img src="/img/instagram-logo-facebook-svgrepo-com.svg" alt="bag icon"
                                            class="icon"></a></li>
                                <li><a href=""><img src="/img/pinterest-svgrepo-com.svg" alt="bag icon" class="icon"></a>
                                </li>
                                <li><a href=""><img src="/img/youtube-rounded-svgrepo-com.svg" alt="bag icon"
                                            class="icon"></a></li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as vars;
@use '../assets/styles/partials/mixin' as mixin;

footer {
    padding: vars.$py-20;
    background-color: vars.$bg_footer ;

    .container {
        max-width: 1200px;
        margin: 30px auto;

        .row {
            @include mixin.flex-wrap;
        }
    }

    .col-100 {
        width: vars.$col-100;

        .d-flex {
            display: flex;
        }

        .space-between {
            justify-content: space-between;
        }
    }

    .h2-footer {
        font-size: vars.$h2-footer;
    }

    .white {
        color: vars.$white_text;
    }

    .my-5 {
        margin: vars.$my-5;
    }

    .f-w-500 {
        font-weight: 500;
    }

    .f-s-14 {
        font-size: vars.$font14;
    }

    .my-10 {
        margin: vars.$my-10;
    }

    .unstyled-list {
        list-style: vars.$unstyled-list;
    }

    .j-start {
        justify-content: start;
    }
}
</style>