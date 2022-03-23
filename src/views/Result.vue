<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">検索結果</h1>
        <p>検索キーワード：{{ $route.params.keyword }}</p>
      </v-col>

      <v-flex mb-4 xs12>
        <div
          style="margin-bottom: 10px; text-align: center"
          v-for="(album, i) in albums"
          :key="i"
        >
          <v-card
            color="gray"
            dark
            :href="album.collectionViewUrl"
            target="_brank"
          >
            <v-card-title class="text-h6" v-text="album.collectionName">
            </v-card-title>

            <v-card-subtitle v-text="album.artistName"></v-card-subtitle>

            <v-card-actions>
              <v-img
                :src="album.artworkUrl100"
                max-height="100"
                max-width="100"
              >
              </v-img>
            </v-card-actions>
          </v-card>
        </div>
      </v-flex>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      albums: [],
    };
  },

  created() {
    const vm = this;
    axios
      .get(
        `https://itunes.apple.com/search?term=${this.$route.params.keyword}&entity=album`
      )
      .then((response) => {
        console.log(response); // eslint-disable-line
        vm.albums = response.data.results;
      });
  },
};
</script>

