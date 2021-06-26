<template>
  <gmap-map :center="center" :zoom="16" style="width: 100%; height: 500px">
    <gmap-marker
      :key="index"
      v-for="(m, index) in markers"
      :position="m.position"
      :title="m.title"
      :clickable="true"
      :draggable="true"
      @click="center = m.position"
    ></gmap-marker>
  </gmap-map>
</template>
<script>
export default {
  data() {
    return {
      center: { lat: 4.5981259, lng: -74.0782322 },
    };
  },
  props: {
    markers: { type: Array, default: [] },
  },
};
</script>
