<template>
  <div style="height: 50vh; width: 50vw;">
    <l-map
      v-model="zoom"
      v-model:zoom="zoom"
      :center="[47.41322, -1.219482]"
      @move="log('move')"
    >
      <l-tile-layer
        url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
      ></l-tile-layer>
      <l-marker
        :lat-lng="[0, 0]"
        draggable
        @moveend="log('moveend')"
      ></l-marker>
    </l-map>
  </div>
</template>
<script>
import { LMap, LTileLayer, LMarker } from "@vue-leaflet/vue-leaflet";
import "leaflet/dist/leaflet.css";

export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
  },
  data() {
    return {
      zoom: 2,
    };
  },
  methods: {
    log(a) {
      console.log(a);
    },
  },
};
</script>
