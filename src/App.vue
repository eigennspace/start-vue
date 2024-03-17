<template>
  <div  class="container my-3">
    <ButtonMemes @termChange="onTermChange"></ButtonMemes>
    <ListMemes :memes="memes"></ListMemes>
  </div>
</template>

<script>
import ListMemes from "@/components/ListMemes.vue";
import ButtonMemes from "@/components/ButtonMemes.vue";
import axios from "axios";

export default {
  name: 'App',
  components: {
    ButtonMemes, ListMemes
  },
  data() {
    return {
      memes: [],
      urlMemes: ''
    }
  },
  mounted() {
    console.log(process.env);
    this.urlMemes = process.env.VUE_APP_LIST_MEMES
  },
  methods: {
    onTermChange() {
      axios
          .get(this.urlMemes)
          .then(res => {
            this.memes = res.data
          })
    }
  }
};
</script>