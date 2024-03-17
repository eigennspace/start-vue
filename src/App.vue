<template>
  <div  class="container my-3">
    <ButtonMemes @termChange="onTermChange"></ButtonMemes>
    <ListMemes :memes="memes"></ListMemes>
  </div>
</template>

<script>
import ListMemes from "@/components/ListMemes.vue";
import ButtonMemes from "@/components/ButtonMemes.vue";
import {URL_MEMES} from "@/constant/UrlMeme";
import axios from "axios";

export default {
  name: 'App',
  components: {
    ButtonMemes, ListMemes
  },
  data() {
    return {
      memes: [],
      URL_MEMES
    }
  },
  methods: {
    onTermChange() {
      axios
          .get(URL_MEMES.LIST_MEMES)
          .then(res => {
            this.memes = res.data
          })
    }
  }
};
</script>