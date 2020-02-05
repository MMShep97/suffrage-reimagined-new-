<template>
    <div class="component-container">
    <loading-screen :is-loading="isLoading"></loading-screen>
      <!-- <div v-if="!isLoading"> -->
      <NavBar />
      <b-container fluid class="body-container">
        <b-row align-h="center">
          <b-col xl="10" lg="12" md="12" sm="12" cols="12">
            <router-view />
          </b-col>
        </b-row>
      </b-container>
      <Footer />
      </div>
</template>

<script>
  import NavBar from '../components/NavBar'
  import Footer from '../components/Footer'
  import LoadingScreen from '../components/helpers/LoadingScreen'
  export default {
    components: {
      NavBar,
      Footer,
      LoadingScreen
    },

    data() {
      return {
        isLoading: true,
      }
    },

    beforeMount() {
      // this.delay(4000);
    },

    mounted() {
      setTimeout(() => {
        this.isLoading = false
      }, 4000)
    },

    methods: {
      delay(ms) {
      const startPoint = new Date().getTime();
      while (new Date().getTime() - startPoint <= ms) {
        /* wait */
      }
    }
    },

    computed: {
      loading: function () {
        return {
          loading: !(this.navLoaded && this.scrapbookLoaded && this.footerLoaded)
        }
      },

      navLoaded() {
        return this.$store.state.isNavLoaded;
      },

      scrapbookLoaded() {
        return this.$store.state.isScrapbookLoaded;
      },

      footerLoaded() {
        return this.$store.state.isFooterLoaded;
      }
    }
  }
</script>