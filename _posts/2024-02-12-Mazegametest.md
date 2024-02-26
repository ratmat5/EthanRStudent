---
toc: true
comments: true
layout: post
title: test
description: Become one with your tools.  They could be more important than code, code, coding.
type: plans
courses: { csse: {week: 0}, csp: {week: 0, categories: [4.A]}, csa: {week: 0} }
categories: [C1.4]
---

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Globe</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
  <style>
    #map {
      height: 500px;
    }
  </style>
</head>
<body>
  <div id="map"></div>

  <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
  <script src="script.js"></script>
</body>
</html>

// Initialize Leaflet map
var map = L.map('map').setView([0, 0], 2); // Center the map and set zoom level

// Add a base map layer (you can use different map styles)
L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
}).addTo(map);

// Add markers for different regions
var markers = [
    {name: 'North America', coordinates: [37.0902, -95.7129]},
    {name: 'Europe', coordinates: [51.1657, 10.4515]},
    {name: 'Asia', coordinates: [34.0479, 100.6197]},
    {name: 'Africa', coordinates: [8.7832, 34.5085]},
    {name: 'South America', coordinates: [-8.7832, -55.4915]},
    {name: 'Australia', coordinates: [-25.2744, 133.7751]}
];

markers.forEach(function(marker) {
    L.marker(marker.coordinates).addTo(map).bindPopup(marker.name);
});
