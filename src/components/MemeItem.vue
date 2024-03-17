<template>
  <div>
    <div class="">

      <li class="list-group-item d-flex ms-auto me-auto justify-content-between align-items-center">
        {{ meme.meme }}
        <span class="badge bg-secondary rounded-pill">🩷 {{ meme.likes }}</span>
      </li>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MemeItem',
  props:['meme']
};
</script>

<style>
li {
  width: 100%;
}
</style>