<template>
  <p>Reaction : {{ scor }} ms</p>
  <p class="rank">Rank : {{ rank }}</p>
</template>

<script>
export default {
  props: ["scor"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.scor < 250) {
      this.rank = "عالیییییییییی بودددد :))))";
    } else if (this.scor < 400) {
      this.rank = "هیییعییی بد نبود :)";
    } else {
      this.rank = "حلزون من کی بوددد :)";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: #0faf87;
  font-weight: bold;
}
</style>
