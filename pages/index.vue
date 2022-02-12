<template>
  <div class="lg:container mx-auto text-3xl my-7 font-bold text-white">
    <div class="p-2 bg-transparent my-2 mx-5">
      <transition name="fade" mode="out-in">
        <div v-if="loading === true" class="text-center font-bold">Loading...</div>
      </transition>
      <transition name="fade" mode="out-in">
        <div v-if="loading === false">
          <div
            style="background-color: rgb(29, 31, 43);"
            class="p-4 text-center md:text-left"
          >PlanetCast Videos</div>
          <div
            class="grid lg:grid-cols-3 xl:grid-cols-4 sm:grid-cols-2 md:grid-cols-3 p-1 m-2 lg:gap-36 text-center mx-auto transition-all duration-500"
          >
            <div v-for="video of videos" :key="video.id.videoId">
              <Video
                :id="video.id.videoId"
                :title="video.snippet.title"
                :image="video.snippet.thumbnails.medium.url"
                :url="'https://youtube.com/watch?v=' + video.id.videoId"
              ></Video>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import Video from "~/components/Video.vue";
export default {
  async mounted() {
    console.log('True')
    this.loading = true;
    let videos = await this.$axios.get('https://www.googleapis.com/youtube/v3/search?key=AIzaSyA6QkJg1UaPfTSo6M-v5H4f9K2q4stBvns&channelId=UChyxJjRhrGa1ohWhKDQsFVQ&part=snippet,id&order=date&maxResults=200')
    videos.data.items = videos.data.items.filter(item => !(item.id.kind === "youtube#channel"));
    this.videos = videos.data.items;
    console.log('Nah')

    this.loading = false;
  },
  name: "IndexPage",
  components: { Video },
  data: () => ({
    loading: true,
    videos: []
  }),
}
</script>


<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 2s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>