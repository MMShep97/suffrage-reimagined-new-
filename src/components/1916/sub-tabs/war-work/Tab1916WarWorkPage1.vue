<template>
  <div class="war-work-page-container">
    <h4 class="page-header text-center">War Work</h4>

    <image-carousel :images="images">
      <template v-slot:textLeft>
        <div class="scrapbook-content-container text-left">
          <div>
            The outbreak of World War I brought new challenges to the suffrage movement. When the U.S. entered
            the war in April
            <b class="embolden">1917</b>, a nationwide propaganda campaign claimed suffragists were unpatriotic
            because they were concentrating on something other than the war effort. Many women laid down
            their suffrage banners for the duration.
          </div>
          <div>
            But others, such as Iowan Anna Bell Lawther, fought hard to make equal suffrage a war measure.
            They argued that if the U.S. wanted to make the world safe for democracy, the country needed to
            grant its own citizens democratic rights. As president of the Iowa Equal Suffrage Association (IESA),
            Lawther formed a Thrift and Agriculture Committee, through which women could work to increase
            Iowa’s food supply in support of the war effort.
          </div>
          <div>
            Iowans received public praise for supporting soldiers, and the IESA reported that war-related
            activities “melted many hearts formerly cold to suffrage.” The increasingly vital presence of
            women in the workforce also helped to diminish the “separate spheres” argument. In fact,
            Lawther credited suffragists’ war work with creating enough support for another suffrage
            amendment to pass the Iowa General Assembly in 1917.
          </div>
          <div>
            That amendment was never discussed during the
            <b class="embolden">1918</b> General Assembly, however, because of a
            clerical error by Secretary of State William S. Allen. Allen claimed the error was not malicious
            and also accused Lawther of not filing the necessary paperwork. The federal amendment passed
            before Iowa lawmakers could discuss the matter again.
          </div>
        </div>
      </template>
    </image-carousel>
  </div>
</template>

<script>
import ImageCarousel from "../../../helpers/ImageCarousel";
import WarworkImage from "../../../../assets/book-content/warwork_large.png";
import PownallImage from "../../../../assets/book-content/pownall_large.png";

export default {
  components: {
    ImageCarousel
  },

  data() {
    return {
      images: [
        {
          url: WarworkImage,
          caption: "SHSI Iowa City.",
          text:
            "Iowa suffragists began war work even before the U.S. officially entered the war in April 1917."
        },
        {
          url: PownallImage,
          caption: "IWA. Dorothy Ashby Pownall Papers.",
          text:
            "Journalist Dorothy Ashby Pownall covered life at Camp Dodge in Johnston, Iowa during World War I, but she also covered the final suffrage convention: “[The suffragists] were always nice to press folks, even though we were inclined to think it rather cute sometimes to be humorous about their eagerness for the vote. We were all for that, too, but we thought some of them occasionally did a good deal of dull talking about it,” speech, Reminiscing to the League of Women Voters in 1955."
        }
      ]
    };
  }
};
</script>

<style scoped>
</style>