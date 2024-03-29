<script lang="ts">
  import MapImports from "mapbox-gl";
  import { onMount, onDestroy } from "svelte";
  import "mapbox-gl/dist/mapbox-gl.css";

  const { Map } = MapImports;
  let map: typeof Map | undefined = undefined;
  let mapContainer: HTMLDivElement;
  let lng: number, lat: number, zoom: number;

  lng = 78.9629;
  lat = 20.5937;
  zoom = 4;

  onMount(() => {
    const initialState = { lng: lng, lat: lat, zoom: zoom };

    map = new Map({
      container: mapContainer,
      accessToken:
        "pk.eyJ1IjoibWFuaWRlZXAtbnVnZ2V0IiwiYSI6ImNsczA4MnY5MjF4ZGwyam14cW9rMXlsbHUifQ.9jFAhaTPQ7bf7G3ugKyr0w",
      style: `mapbox://styles/mapbox/outdoors-v11`,
      center: [initialState.lng, initialState.lat],
      zoom: initialState.zoom,
    });
  });

  onDestroy(() => {
    map?.remove();
  });
</script>

<div class="map-wrap">
  <div class="sidebar">
    Longitude: {lng.toFixed(4)} | Latitude: {lat.toFixed(4)} | Zoom: {zoom.toFixed(2)}
  </div>
  <div class="map" bind:this={mapContainer} />
</div>

<style>
  .map-wrap {
    position: relative;
    width: 100%;
    height: 100%;
    align-self: stretch;
    flex: 1;
  }
  .map {
    position: absolute;
    width: 100%;
    height: 100%;
    align-self: stretch;
  }
  .sidebar {
    background-color: rgb(35 55 75 / 90%);
    color: #fff;
    padding: 6px 12px;
    font-family: monospace;
    z-index: 1;
    position: absolute;
    top: 0;
    left: 0;
    margin: 12px;
    border-radius: 4px;
  }
</style>
