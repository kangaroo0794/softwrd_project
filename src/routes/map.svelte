<script>
    import { onMount } from 'svelte';
    import Map from 'ol/Map';
    import View from 'ol/View';
    import TileLayer from 'ol/layer/Tile';
    import OSM from 'ol/source/OSM';
    import GeoJSON from 'ol/format/GeoJSON';
    import VectorLayer from 'ol/layer/Vector';
    import VectorSource from 'ol/source/Vector';
    import Style from 'ol/style/Style';
    import Fill from 'ol/style/Fill';
    
    let map;
    
    onMount(async () => {
      // Initialize the map
      map = new Map({
        target: 'map',
        layers: [
          new TileLayer({
            source: new OSM(),
          }),
        ],
        view: new View({
          center: [0, 0],
          zoom: 2,
        }),
      });
      try {
      const geoJSONResponse = await fetchGeoJSON();
      const geoJSONData = geoJSONResponse.data;
  
      const vectorSource = new VectorSource({
        features: new GeoJSON().readFeatures(geoJSONData),
      });
  
      const vectorLayer = new VectorLayer({
        source: vectorSource,
        style: new Style({
          fill: new Fill({
            color: '#006a4e', 
          }),
        }),
        opacity: 0.75, 
      });
  
      map.addLayer(vectorLayer);
    } catch (error) {
      console.error('Error loading GeoJSON data:', error);
    }
  });
  
  async function fetchGeoJSON() {
    try {
      const response = await fetch(
        'https://raw.githubusercontent.com/datasets/geo-countries/master/data/countries.geojson'
      );
      const data = await response.json();
      return data;
    } catch (error) {
      throw error;
    }
  }
</script>

<style>
  #map {
    width: 100%;
    height: 100vh; 
  }
</style>

<div id="map"></div>