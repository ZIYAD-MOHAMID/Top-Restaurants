<script setup lang="ts">
const props = defineProps<RowProps>();
interface RowProps {
  rank?: number;
  name?: string;
  index?: number;
  isHeader?: boolean;
}
</script>

<template>
  <div class="row" v-if="isHeader">
    <h4 class="header">Rank</h4>
    <h4 class="header">Chain</h4>
  </div>
  <div
    v-else
    class="row"
    :style="
      index % 2 === 0
        ? { background: 'rgba(128,128,128,0.15)' }
        : { background: 'hsla(0, 0%, 62%, 0.819)' }
    "
  >
    <h4 class="header rank">{{ rank }}</h4>
    <NuxtLink :to="`/restaurants/${name}`" class="header link">{{
      name
    }}</NuxtLink>
  </div>
</template>

<style scoped>
.row {
  border-top: 1px solid rgba(128, 128, 128, 0.336);
  display: flex;
  align-items: center;
}
.header {
  font-size: 1.25rem;
  color: hsla(253, 82%, 30%, 0.819);
  margin: 0;
  margin-right: 2rem;
  padding: 0.5rem 1rem;
  font-weight: 700;
  width: 4rem;
}
.rank {
  color: black;
}
.link {
  text-decoration: none;
  color: rgb(228, 157, 27);
  width: auto;
  font-weight: 500;
}
</style>
