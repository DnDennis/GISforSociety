<!DOCTYPE html>
  <html>

    <head>
		<title> My first leaflet map </title>
		<link rel="stylesheet" href="main.css"/>
		<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A==" crossorigin="" />
    </head>
	<body>
		<H1>Example</H1>	
		<div id="map"></div>
		<script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js" integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA==" crossorigin=""></script>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet-hash/0.2.1/leaflet-hash.js"></script>
		<script>
			const map = L.map('map').setView([51.9741, 5.6688], 15);
			const hash = new L.Hash(map);
			const backgroundMap = L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
				maxZoom: 19,
				attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
				}
			);
			let marker = L.marker([51.98514, 5.66647]).addTo(map);
			let forum = L.marker([ 51.98531, 5.66361]).addTo(map);
			let popup = "Forum";
			forum.bindPopup(popup); 
			let circle =  L.circle([51.98531, 5.66361], 500, {
			  color: 'red',
			  fillColor: '#f03',
			  fillOpacity: 0.5
			}).addTo(map);
			let polygon = L.polygon(
			  [[
				[51.98675, 5.66554], 
				[51.9875, 5.66832], 
				[51.98825, 5.66778], 
				[51.98779, 5.66602], 
				[51.98784, 5.66591], 
				[51.98758, 5.66501], 
				[51.98753, 5.66498], 
				[51.98675, 5.66554]
			  ]]).addTo(map);
			backgroundMap.addTo(map);
			

		</script>
	</body>
</html>
