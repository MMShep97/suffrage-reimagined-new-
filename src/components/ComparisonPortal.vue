<template>
    <div class="component-container md-elevation-20">
        <b-container fluid>
            <b-row align-v="start">
                <b-col>test</b-col>
                <b-col>test</b-col>
                <b-col>test</b-col>
            </b-row>
            <b-row align-v="center">
                <b-col>test</b-col>
                <b-col><b-img-lazy :src="oldBook"></b-img-lazy></b-col>
                <b-col>
                    test
                </b-col>
            </b-row>
            <b-row align-v="end">
                <b-col>test</b-col>
                <b-col>test</b-col>
                <b-col>
                    test
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
import oldBook from './../assets/scrapbook-extras/comparison-portal/old-book.jpg'

export default {
    data() {
        return {
            oldBook: oldBook
        }
    }
}
</script>

<style scoped>
.component-container {
    background-color: black;
    border: .3em solid #FFCD00;
    position: fixed;
    width: 100%;
    height: 100%;
    margin: 0 auto;
    padding: 0 0;
    color: white;
    text-align: center;
}

.container-fluid {
    height: 100%;
    width: 100%;
}

.row {
    height: 33%;    
}
</style>