<template>
  <div id="mapContainer" class="basemap"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
  name: "BaseMap",
  data() {
    return {
      accessToken:
        "pk.eyJ1IjoiYW1pcnBlYWNlMTA4MCIsImEiOiJja3lrYXExaWkwYWRzMnZwZXU0bWRlbzVkIn0.ot6KCZlh8EH4PjMA_146kg",
    };
  },
  mounted() {
    mapboxgl.accessToken = this.accessToken;

    new mapboxgl.Map({
      container: "mapContainer",
      style: "mapbox://styles/mapbox/streets-v11",
      center: [103.811279, 1.345399],
      zoom: 12,
      maxBounds: [
        [103.6, 1.1704753],
        [104.1, 1.4754753],
      ],
    });
  },
};
</script>

<style lang="scss" scoped>
.basemap {
  width: 100%;
  height: 100%;
}
</style>
