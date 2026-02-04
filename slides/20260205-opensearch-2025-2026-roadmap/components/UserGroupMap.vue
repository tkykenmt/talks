<script setup>
import { onMounted } from 'vue'

const mapId = 'usergroup-map-' + Math.random().toString(36).substr(2, 9)

const userGroups = [
  { city: 'Coimbatore', lat: 11.02, lng: 76.96, name: 'OpenSearch Project Coimbatore', url: 'https://www.meetup.com/opensearch-project-coimbatore' },
  { city: 'Jaipur', lat: 26.92, lng: 75.8, name: 'OpenSearch User Group Jaipur', url: 'https://www.meetup.com/opensearch-ug-jaipur' },
  { city: 'Ahmedabad', lat: 23.03, lng: 72.58, name: 'OpenSearch Project Ahmedabad', url: 'https://www.meetup.com/opensearch-project-ahmedabad' },
  { city: 'Singapore', lat: 1.3, lng: 103.85, name: 'OpenSearch Project Singapore', url: 'https://www.meetup.com/opensearch-project-singapore' },
  { city: 'Roma', lat: 41.9, lng: 12.48, name: 'OpenSearch Project Rome', url: 'https://www.meetup.com/opensearch-project-rome' },
  { city: 'Washington DC', lat: 38.91, lng: -77.02, name: 'OpenSearch Project Washington DC', url: 'https://www.meetup.com/opensearch-project-washington-dc' },
  { city: 'Chennai', lat: 13.09, lng: 80.27, name: 'OpenSearch Project Chennai', url: 'https://www.meetup.com/opensearch-project-chennai' },
  { city: 'Cape Town', lat: -33.93, lng: 18.46, name: 'OpenSearch Project Cape Town', url: 'https://www.meetup.com/opensearch-project-cape-town' },
  { city: 'Cairo', lat: 30.06, lng: 31.25, name: 'OpenSearch Project Cairo', url: 'https://www.meetup.com/opensearch-project-cairo' },
  { city: 'Sydney', lat: -33.87, lng: 151.21, name: 'OpenSearch Project Sydney', url: 'https://www.meetup.com/opensearch-project-sydney' },
  { city: 'Lisbon', lat: 38.72, lng: -9.14, name: 'Lisbon Search and AI User Group', url: 'https://www.meetup.com/search-and-ai-lisbon' },
  { city: 'Pforzheim', lat: 48.89, lng: 8.69, name: 'OpenSearch Project Karlsruhe-Pforzheim', url: 'https://www.meetup.com/opensearch-project-pforzheim' },
  { city: 'São Paulo', lat: -23.53, lng: -46.63, name: 'OpenSearch Project São Paulo', url: 'https://www.meetup.com/opensearch-project-sao-paulo' },
  { city: 'Hyderabad', lat: 17.4, lng: 78.48, name: 'OpenSearch Project Hyderabad', url: 'https://www.meetup.com/opensearch-project-hyderabad' },
  { city: 'Vienna', lat: 48.22, lng: 16.37, name: 'OpenSearch Project Vienna', url: 'https://www.meetup.com/opensearch-project-vienna' },
  { city: 'Melbourne', lat: -37.81, lng: 144.96, name: 'Melbourne Search & AI User Group', url: 'https://www.meetup.com/opensearch-project-melbourne' },
  { city: 'Bengaluru', lat: 12.97, lng: 77.59, name: 'OpenSearch Project Bengaluru', url: 'https://www.meetup.com/opensearch-project-bengaluru' },
  { city: 'Boston', lat: 42.36, lng: -71.07, name: 'OpenSearch Project Boston', url: 'https://www.meetup.com/opensearch-project-boston' },
  { city: 'Pune', lat: 18.53, lng: 73.84, name: 'OpenSearch Project Pune', url: 'https://www.meetup.com/opensearch-project-pune' },
  { city: 'Milano', lat: 45.46, lng: 9.19, name: 'OpenSearch Project Milan', url: 'https://www.meetup.com/opensearch-project-milan' },
  { city: 'Tel Aviv', lat: 32.07, lng: 34.77, name: 'OpenSearch Project Tel Aviv Yafo', url: 'https://www.meetup.com/opensearch-project-tel-aviv-yafo' },
  { city: 'Tokyo', lat: 35.67, lng: 139.77, name: 'OpenSearch Project Tokyo', url: 'https://www.meetup.com/opensearch-project-tokyo', highlight: true },
  { city: 'Berlin', lat: 52.52, lng: 13.38, name: 'OpenSearch Project Berlin', url: 'https://www.meetup.com/opensearch-project-berlin' },
  { city: 'San Francisco', lat: 37.78, lng: -122.42, name: 'OpenSearch Project Bay Area', url: 'https://www.meetup.com/opensearch-project-bay-area' },
  { city: 'Seoul', lat: 37.56, lng: 126.99, name: 'OpenSearch Project - Seoul', url: 'https://www.meetup.com/opensearch-project-seoul' },
  { city: 'London', lat: 51.54, lng: -0.08, name: 'London Search & AI User Group', url: 'https://www.meetup.com/search-and-ai-london' },
  { city: 'Paris', lat: 48.86, lng: 2.34, name: 'OpenSearch Project - Paris', url: 'https://www.meetup.com/opensearch-project-paris' },
  { city: 'München', lat: 48.14, lng: 11.58, name: 'OpenSearch Project - München', url: 'https://www.meetup.com/opensearch-project-munchen' },
  { city: 'Vancouver', lat: 49.28, lng: -123.04, name: 'OpenSearch Project Vancouver BC', url: 'https://www.meetup.com/opensearch-project-vancouver-bc' },
  { city: 'Dublin', lat: 53.33, lng: -6.25, name: 'OpenSearch Project Dublin', url: 'https://www.meetup.com/opensearch-project-dublin' },
  { city: 'New York', lat: 40.75, lng: -73.99, name: 'New York City OpenSearch User Group', url: 'https://www.meetup.com/new-york-city-opensearch-user-group' },
  { city: 'Austin', lat: 30.22, lng: -97.75, name: 'OpenSearch Project - Austin', url: 'https://www.meetup.com/opensearch-project-austin' },
  { city: 'Amsterdam', lat: 52.37, lng: 4.89, name: 'OpenSearch Project - Amsterdam', url: 'https://www.meetup.com/opensearch-project-amsterdam' },
  { city: 'Bristol', lat: 51.46, lng: -2.6, name: 'Bristol Open Source Search Boss Meetup', url: 'https://www.meetup.com/opensearch-project-bristol' },
  { city: 'Seattle', lat: 47.61, lng: -122.33, name: 'OpenSearch Project - Seattle', url: 'https://www.meetup.com/opensearch-project-seattle' },
  { city: 'Chicago', lat: 41.88, lng: -87.62, name: 'Chicago Search Community', url: 'https://www.meetup.com/opensearch-project-chicago' },
  { city: 'Portland', lat: 45.5, lng: -122.69, name: 'OpenSearch Community & Triage Meetings', url: 'https://www.meetup.com/opensearch' },
]

onMounted(async () => {
  const link = document.createElement('link')
  link.rel = 'stylesheet'
  link.href = 'https://unpkg.com/leaflet@1.9.4/dist/leaflet.css'
  document.head.appendChild(link)

  const script = document.createElement('script')
  script.src = 'https://unpkg.com/leaflet@1.9.4/dist/leaflet.js'
  document.head.appendChild(script)

  script.onload = () => {
    const L = window.L
    const map = L.map(mapId, { zoomControl: false, attributionControl: false }).setView([25, 20], 2)
    L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}').addTo(map)

    userGroups.forEach(ug => {
      const color = ug.highlight ? '#0ea5e9' : '#005EB8'
      const marker = L.circleMarker([ug.lat, ug.lng], {
        radius: 8,
        fillColor: color,
        color: ug.highlight ? '#fff' : '#003366',
        weight: ug.highlight ? 3 : 2,
        fillOpacity: 0.9
      }).addTo(map)

      marker.bindPopup(`
        <div style="text-align:center;">
          <b>${ug.name}</b><br/>
          <span style="color:#666;">${ug.city}</span><br/>
          <a href="${ug.url}" target="_blank" style="color:#0ea5e9;">Meetup →</a>
        </div>
      `, { maxWidth: 220 })
    })
  }
})
</script>

<template>
  <div :id="mapId" class="w-full h-72 rounded-lg" style="background: #e8e8e8;"></div>
</template>
