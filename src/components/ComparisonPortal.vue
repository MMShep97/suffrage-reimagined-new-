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
                <!-- <b-col>test</b-col>
                <b-col>

                </b-col>
                <b-col>test</b-col> -->
            </b-row>
            <b-row align-v="center">
                <b-col>
                    <md-card class="old-site-card site-card" md-with-hover>
                        <md-ripple>
                            <a href="http://sdrc.lib.uiowa.edu/exhibits/suffrage/index.html">
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
</a>
                            <!-- </router-link> -->
                        </md-ripple>

                    </md-card>
                </b-col>
                <!-- <b-col></b-col><b-col><b-img-lazy :src="oldBook"></b-img-lazy></b-col> -->
                <b-col>
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

                            </router-link>
                        </md-ripple>

                    </md-card>
                </b-col>
            </b-row>
            <b-row align-v="end">
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

    export default {
        data() {
            return {
                oldBook: oldBook,
                libraryLogo: libraryLogo
            }
        },

        methods: {
            notifyApp: function(event) {
                this.$emit('clicked', true)
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

    .site-card {
        width: 800px;
        margin: 25px auto;
        box-shadow: 0 3px 1px -2px rgb(255, 255, 255, 0.20), 0 2px 2px 0 rgb(255, 255, 255, 0.14), 0 1px 5px 0 rgba(255, 255, 255, 0.12);
        background-color: rgba(255, 255, 255, 0.76) !important;
    }

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