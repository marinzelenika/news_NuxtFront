<template>
  <div>
    <p v-if="$fetchState.pending">Fetching news...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <div class="container">
          <div class="card-deck row">
              <div class="col-sm" v-for="article of news.data">
              <div class="card">
                <img
                  class="card-img-top"
                  v-bind:src="article.image_url"
                  alt="Card image cap"
                />
                <div class="card-body">
                  <h5 class="card-title">{{ article.title }}</h5>
                  <p class="card-text">
                    {{ article.description }}
                  </p>
                  <p class="card-text">
                    <small class="text-muted"
                      >published at {{ article.published_at }}</small
                    >
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  
</template>

<script>
export default {
  data() {
    return {
      news: []
    };
  },

  async fetch() {
    this.news = await fetch(
      "https://api.thenewsapi.com/v1/news/top?api_token=Zumz4iyBOwObJx2VrMkrtNJ0crcN7F1K2M9XqGQU&locale=us&limit=3"
    ).then(res => res.json());
  }
};
</script>

<style lang="scss" scoped>
img {
  float: left;
  width: 362px;
  height: 200px;
  object-fit: cover;
}
.card{
    width: 362px;
    height: 460px;
    margin-top: 20px;
}
</style>
