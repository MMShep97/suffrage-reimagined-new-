<template>
    <div class="component-container">
        <b-container fluid>
            <b-row>
                <!-- <b-col><div class="component-title">Women's Suffrage in Iowa<div class="break"></div>The Scrapbook</div></b-col> -->
                <b-col>
                    <b-jumbotron class="header-jumbotron"><template v-slot:header><span
                                style="color: rgba(255, 255, 255, 0.61);">Welcome to the</span> <span
                                style="color: #FFCD00">Women's Suffrage in Iowa Scrapbook</span></template>

                        <template v-slot:lead>
                            <hr class="my-4 line-separator">
                            <p>The scrapbook's aesthetic has been redesigned &amp; revamped to celebrate the 100th
                                anniversary of Women's Suffrage.</p>
                            <p>Please feel free to choose below from either the new or old site; the content is still
                                the same!</p>
                            <hr class="my-4 line-separator">
                        </template></b-jumbotron>
                </b-col>

            </b-row>
            <b-row align-v="center">
                <b-col sm="6" cols="6">
                    <md-card class="old-site-card site-card" md-with-hover>
                        <md-ripple>
                            <a
                                href="https://web.archive.org/web/20190316221349/http://sdrc.lib.uiowa.edu/exhibits/suffrage/index.html">
                                <!-- <router-link to="/1854">  -->
                                <md-card-header>
                                    <md-card-header-text>
                                        <div class="md-title">Women's Suffrage</div>
                                        <div class="md-subhead">The Old Scrapbook</div>
                                    </md-card-header-text>

                                    <md-card-media>
                                        <img :src="libraryLogo" alt="People">
                                    </md-card-media>
                                </md-card-header>
                                <md-card-content class="card-content">Test Content</md-card-content>

                            </a>
                            <!-- </router-link> -->
                        </md-ripple>

                    </md-card>
                </b-col>
                <!-- <b-col></b-col><b-col><b-img-lazy :src="oldBook"></b-img-lazy></b-col> -->
                <b-col sm="6" cols="6">
                    <md-card class="new-site-card site-card" md-with-hover>
                        <md-ripple>

                            <router-link @click.native="notifyApp()" to="">
                                <md-card-header>
                                    <md-card-header-text>
                                        <div class="md-title">Suffrage Reimagined</div>
                                        <div class="md-subhead">The New Scrapbook</div>
                                    </md-card-header-text>
                                    

                                    <md-card-media>
                                        <img :src="libraryLogo" alt="People">
                                    </md-card-media>
                                </md-card-header>
                                <md-card-content class="card-content">Test Content</md-card-content>

                            </router-link>
                        </md-ripple>

                    </md-card>
                </b-col>
            </b-row>
            <b-row align-v="end" class="iowa-ratify-image-container">
                <b-img-lazy class="iowa-ratify-image" :src="iowaRatification"></b-img-lazy>
                <!-- <b-col>test</b-col>
                <b-col>test</b-col>
                <b-col>
                    test
                </b-col> -->
            </b-row>
        </b-container>
    </div>
</template>

<script>
    import oldBook from './../assets/scrapbook-extras/comparison-portal/old-book.jpg'
    import libraryLogo from '../../public/images/iowa_logo_retro.png'
    import iowaRatification from "./../assets/scrapbook-extras/comparison-portal/iowa-ratify.png"

    export default {
        data() {
            return {
                oldBook: oldBook,
                libraryLogo: libraryLogo,
                iowaRatification: iowaRatification
            }
        },

        methods: {
            notifyApp: function (event) {
                this.$emit('clicked', true)
            },
            isMobile() {
                return this.window.width < 1000 ? true : false
            }
        }
    }
</script>

<style scoped>
    .component-container {
        background-color: rgb(0, 0, 0);
        /* border: .1em solid black; */
        position: fixed;
        width: 100%;
        height: 100%;
        padding: 20px 20px;
        color: white;
    }

    .container-fluid {
        height: 100%;
        width: 100%;
    }


    .header-jumbotron {
        background-color: black !important;
        text-align: center;
    }

    .jumbotron {
        margin-bottom: 0 !important;
        padding-bottom: 0 !important;
    }

    .iowa-ratify-image {
        margin-right: auto;
        margin-left: auto;
        margin-top: 4em;
        filter: drop-shadow(16px 16px 20px #FFCD00) invert(100%);
    }

@media only screen and (max-width: 2200px) { .display-3 { font-size: 4rem;} }
@media only screen and (max-width: 1900px) { .display-3 { font-size: 3rem;} }
@media only screen and (max-width: 1500px) { .display-3 { font-size: 2rem;} }

.card-content {
    font-weight: normal !important;
}


    .site-card {
        margin: 25px auto;
        box-shadow: 0 3px 1px -2px rgb(255, 255, 255, 0.20), 0 2px 2px 0 rgb(255, 255, 255, 0.14), 0 1px 5px 0 rgba(255, 255, 255, 0.12);
        background-color: rgba(255, 255, 255, 0.76) !important;
    }

    @media only screen and (max-width: 500px) { .site-card { font-size: 10px; }}

    .site-card a {
        color: black !important;
        text-decoration: none !important;
    }

    .md-title {}

    .site-card:hover {
        /* box-shadow: 0 3px 1px -2px rgb(255, 255, 255, 0.20), 0 2px 2px 0 rgb(255, 255, 255, 0.14), 0 1px 5px 0 rgba(255, 255, 255, 0.12); */
    }

    .md-with-hover:hover {
        /* box-shadow: 0 3px 1px -2px rgb(255, 255, 255, 0.20), 0 2px 2px 0 rgb(255, 255, 255, 0.14), 0 1px 5px 0 rgba(255, 255, 255, 0.12) !important; */
        box-shadow: 0 5px 5px -3px rgba(255, 255, 255, .2), 0 8px 10px 1px rgba(255, 255, 255, .14), 0 3px 14px 2px rgba(255, 255, 255, .12) !important;
    }

    .line-separator {
        background-color: rgba(255, 255, 255, 0.61);
    }

    .old-site-card {}

    .new-site-card {}
</style>