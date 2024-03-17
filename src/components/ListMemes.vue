<template>
  <div>
    <ul class="list-group">
      <MemeItem
          v-for="meme in memes"
          :key="meme.id"
          :meme="meme">
      </MemeItem>
    </ul>
  </div>
</template>

<script>
import MemeItem from "@/components/MemeItem.vue";

export default {
  name: 'ListMemes',
  components: {
    MemeItem
  },
  props: ['memes'],
};
</script>