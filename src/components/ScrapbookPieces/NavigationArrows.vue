<template>
    <div class="nav-arrows">
        <div v-if="isMobile()">
            <md-button v-show="hasPreviousPage" @click="prevTab()" class="go-back-arrow-mobile md-icon-button md-elevation-24"
                name="page-arrow-go-back">
                <md-icon :md-src="arrowLeftWhite" class="icon" />
            </md-button>
            <md-button v-show="hasNextPage" @click="nextTab()" class="go-forward-arrow-mobile md-icon-button md-elevation-24"
                name="page-arrow-go-forward">
                <md-icon :md-src="arrowRightWhite" class="icon" />
            </md-button>
        </div>
        <div v-else>
            <md-button v-show="hasPreviousPage" @click="prevTab()" @mouseover="arrowLeft = arrowLeftBlack"
                @mouseleave="arrowLeft = arrowLeftWhite" class="go-back-arrow md-icon-button" name="page-arrow-go-back">
                <transition name="fade" mode="out-in">
                    <!-- <img :src="arrowLeft" :key="arrowLeft"/> -->
                    <md-icon :md-src="arrowLeft" class="icon" :key="arrowLeft" />
                </transition>
            </md-button>


            <md-button v-show="hasNextPage" @click="nextTab()" @mouseover="arrowRight = arrowRightBlack"
                @mouseleave="arrowRight = arrowRightWhite" class="go-forward-arrow md-icon-button"
                name="page-arrow-go-forward">
                <transition name="fade" mode="out-in">

                    <!-- <img class=""  src="../../assets/scrapbook-extras/arrow-right-white.png"> -->
                    <md-icon :md-src="arrowRight" class="icon" :key="arrowRight" />
                </transition>
            </md-button>
        </div>
    </div>
</template>

<script>
    import {
        routeNames
    } from '../../router/index'

    import ArrowLeftWhite from '../../assets/scrapbook-extras/arrow-left-white.svg'
    import ArrowLeftBlack from '../../assets/scrapbook-extras/arrow-left-black.svg'

    import ArrowRightBlack from '../../assets/scrapbook-extras/arrow-right-black.svg'
    import ArrowRightWhite from '../../assets/scrapbook-extras/arrow-right-white.svg'
    export default {

        data() {
            return {
                routes: routeNames,
                arrowLeftWhite: ArrowLeftWhite,
                arrowLeftBlack: ArrowLeftBlack,
                arrowLeft: ArrowLeftWhite,

                arrowRightWhite: ArrowRightWhite,
                arrowRightBlack: ArrowRightBlack,
                arrowRight: ArrowRightWhite,

                window: {
                    width: 0,
                    height: 0,
                }
            }
        },

        created() {
            window.addEventListener('resize', this.handleResize)
            this.handleResize();
        },

        destroyed() {
            window.removeEventListener('resize', this.handleResize)
        },

        computed: {
            hasPreviousPage: function () {
                let index = this.routes.indexOf(this.$route.name)
                return this.routes[index - 1]
            },

            hasNextPage: function () {
                let index = this.routes.indexOf(this.$route.name)
                return this.routes[index + 1]
            }
        },


        methods: {
            handleResize() {
                this.window.width = window.innerWidth;
                this.window.height = window.innerHeight;
            },

            isMobile() {
                return this.window.width < 1200 ? true : false
            },

            prevTab() {
                let index = this.routes.indexOf(this.$route.name);
                if (this.routes[index - 1]) {
                    this.$router.push({
                        name: this.routes[index - 1]
                    });
                }
            },
            nextTab() {
                let index = this.routes.indexOf(this.$route.name);
                if (this.routes[index + 1]) {
                    this.$router.push({
                        name: this.routes[index + 1]
                    });
                }
            },
        }
    }
</script>

<style scoped>
    .icon {
        width: 100%;
        height: 100%;
    }

    .go-back-arrow {
        /* top: 35rem;
        left: -6rem; */
        top: 50vh;
        left: 4rem;
    }

    .go-forward-arrow {
        top: 50vh;
        right: 4rem;
        /* top: 35rem;
        right: -6rem; */
    }

    .go-back-arrow,
    .go-forward-arrow {
        position: fixed;
        opacity: 0.2;
        transform: scale(1.3);
        /* width: 80px;
        height: auto;
        padding: 0 0; */
    }

    .go-back-arrow:hover {
        opacity: 1
    }

    .go-forward-arrow:hover {
        opacity: 1
    }

    .go-back-arrow-mobile {
        top: 50%;
        left: .5rem;
    }

    .go-forward-arrow-mobile {
        top: 50%;
        right: .5rem;
    }

    .go-back-arrow-mobile,
    .go-forward-arrow-mobile {
        position: fixed;
        opacity: 0.2;
    }

    .go-back-arrow-mobile:hover {
        opacity: 1;
    }

    .go-forward-arrow-mobile:hover {
        opacity: 1;
    }




    .fade-enter-active,
    .fade-leave-active {
        transition: opacity .3s ease-in-out;
    }

    .fade-enter,
    .fade-leave-to {
        opacity: 0;
    }

    .fade-enter-to,
    .fade-leave {
        opacity: 1;
    }
</style>