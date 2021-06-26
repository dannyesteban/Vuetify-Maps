<template>
  <div>
    <h2>Mapa</h2>
    <br />
    <GoogleMaps :markers="places" />
  </div>
</template>

<script>
import GoogleMaps from "../components/GoogleMaps";

export default {
  components: {
    GoogleMaps,
  },
  data: () => ({
    places: [
      {
        position: { lat: 4.5981259, lng: -74.0782322 },
        title: "Plaza de Bolivar",
      },
      {
        position: { lat: 4.6001747, lng: -74.075099 },
        title: "Museo del Oro",
      },
    ],
  }),
};
</script>

