<template>
  <v-timeline class="ma-16" align="start">
    <v-timeline-item
      v-for="(year, i) in years"
      :key="i"
      :dot-color="year.color"
      size="small"
    >
      <template v-slot:opposite>
        <div
          :class="`pt-1 headline font-weight-bold text-${year.color}`"
          v-text="year.year"
        ></div>
      </template>
      <div>
        <h2 :class="`mt-n1 headline font-weight-light mb-4 text-${year.color}`">
          {{ year.history[0] }}
        </h2>
        <div>
          {{ year.history[1] }}
        </div>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>
<script>
  import feed from '../data/lineHistory.json'
  export default {
    data: () => ({
      years: feed
    }),
  }
</script>
