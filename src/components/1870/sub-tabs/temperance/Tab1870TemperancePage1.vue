<template>
  <div class="page-container">
    <h4 class="text-center">Voting for Temperance</h4>
    <image-carousel :images="images">
      <template v-slot:textLeft>
        <div class="scrapbook-content-container text-left">
          <div>
            A temperance movement advocating the reduced use or banning of alcoholic beverages began in the early
            <b
              class="embolden"
            >1800s</b>. Temperance overlapped and intertwined with suffrage throughout its history, but especially in the
            period from
            <b class="embolden">1870 to 1890</b>.
          </div>

          <div>
            In the nineteenth century, alcoholism was rampant and there were few social programs designed to help.
            Women and children were vulnerable to abuse by drunk husbands or fathers. Without a political voice,
            women and children lacked recourse.
          </div>

          <div>
            In
            <b class="embolden">1874</b>, the Woman’s Christian Temperance Union (WCTU) was founded in Ohio. By the
            <b class="embolden">1880s</b>, it was the
            largest women’s organization in the United States. According to an
            <b class="embolden">1884</b> report, an estimated 5,000 Iowa
            women had joined.
          </div>

          <div>
            In her
            <b class="embolden">1883</b> address to the Iowa WCTU, corresponding secretary Lizzie D. Carhart wrote that women had
            previously been reluctant to talk about getting the vote, but they began to see it as “a weapon for the
            protection of their homes.”
          </div>

          <div>
            The WCTU had a "do everything" policy, which meant it was a base for many reform causes besides
            temperance. Since it drew its membership from women’s clubs and organizations already in place in
            Protestant churches, the WCTU was considered a respectable avenue for reform.
          </div>
        </div>
      </template>
    </image-carousel>
  </div>
</template>

<script>
import ImageCarousel from "../../../helpers/ImageCarousel";
import ProceedingsImage from "../../../../assets/book-content/proceedings_large.png";
import CarhartImage from "../../../../assets/book-content/carhart_large.png";
import DenisonImage from "../../../../assets/book-content/denison_large.png";

export default {
  components: {
    ImageCarousel
  },

  data() {
    return {
      images: [
        {
          url: ProceedingsImage,
          caption: "IWA. Woman's Christian Temperance Union Records.",
          text:
            "In 1877, the Iowa WCTU officially endorsed equal suffrage, believing that women would vote for temperance legislation. The national organization did not officially endorse suffrage until 1883. By 1886, the Iowa WCTU had a whole department devoted to securing the franchise"
        },
        {
          url: CarhartImage,
          caption: "IWA. Woman's Christian Temperance Union Records.",
          text: "Lizzie D. Carhart, Iowa WCTU leader, 1916."
        },
        {
          url: DenisonImage,
          caption: "IWA. Woman's Christian Temperance Union Records.",
          text:
            "This minute book (1878 - 1880) is from the Denison Total Abstinence Union, which was a temperance organization also open to men. In May of 1879, the members debated whether or not the U.S. would benefit from having women vote on the “liquor question.” The club decided in the affirmative."
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>