<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Taman Laut Olele</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
    <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            background-color: #f4f4f4;
        }
        .container {
            padding: 20px;
            max-width: 800px;
            margin: auto;
            background-color: #fff;
            border-radius: 12px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .header {
            position: relative;
            color: white;
        }
        .header img {
            width: 100%;
            height: 350px;
            object-fit: cover;
            border-radius: 12px;
        }
        .header .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            border-radius: 12px;
        }
        .header .text-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            width: 80%;
        }
        .header .text-container h1 {
            font-size: 24px;
            margin-bottom: 10px;
            color: white;
        }
        .header .text-container p {
            font-size: 16px;
            margin-bottom: 5px;
            color: white;
        }
        .logo-menu {
            position: absolute;
            top: 20px;
            left: 20px;
            display: flex;
            align-items: center;
        }
        .logo-menu img {
            width: 100px;
            height: auto;
            margin-right: 350px;
        }
        .logo-menu nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            display: flex;
        }
        .logo-menu nav ul li {
            display: inline;
            margin-right: 20px;
        }
        .logo-menu nav ul li a {
            color: white;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
        }
        .logo-menu nav ul li a:hover {
            text-decoration: underline;
        }
        .info-container {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }
        .info {
            width: 48%;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 12px;
            box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.1);
        }
        .info h2 {
            text-align: center;
        }
        .info ul {
            list-style: none;
            padding: 0;
        }
        .info ul li {
            margin-bottom: 10px;
        }
        .separator {
            border-bottom: 1px solid #a7a6a6;
            margin: 10px 0;
        }
        .address {
            width: 48%;
            text-align: center;
        }
        .address img {
            width: 100%;
            border-radius: 12px;
            margin-bottom: 10px;
        }
        .address p {
            font-size: 14px;
            margin: 5px 0;
        }
        .address span {
            font-size: 14px;
            font-weight: bold;
        }
        .address p span {
            font-weight: normal;
        }
        .address a {
            font-size: 14px;
            text-decoration: none;
            color: #00BFFF;
        }
        .description {
            border: 1px solid #a7a6a6;
            padding: 10px;
            border-radius: 12px;
            box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.1);
            text-align: center;
            margin-bottom: 20px;
        }
        .description h2 {
            text-align: center;
        }
        .description p {
            text-align: center;
        }
        .image-gallery {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }
        .image-gallery img {
            width: 48%;
            border-radius: 12px;
        }
        .centered-image {
            display: flex;
            justify-content: center;
        }
        .map {
            width: 75%;
            height: 300px;
            border-radius: 12px;
        }
        .judul h1 {
            text-align: center;
            color: #00BFFF;
        }
    </style>
</head>
<body onload="initMap()">

<div class="container">
    <div class="header">
        <img src="persebaran 1.jpg" alt="Background">
        <div class="overlay"></div>
        <div class="text-container">
            <h1>"Jelajahi Surga Pesisir Gorontalo"</h1>
            <p>"Jelajahi keajaiban alam yang memikat di tepian pantai Gorontalo"</p>
            <p>Temukan Keajaiban Laut Gorontalo Destinasi Perjalananmu Menuju Ketenangan dan Kebahagiaan."</p>
        </div>
        <div class="logo-menu">
            <img src="persebaran_logo.png" alt="Logo">
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Data Tempat Wisata</a></li>
                    <li><a href="#">About Us</a></li>
                </ul>
            </nav>
        </div>
    </div>
    <div class="judul">
        <h1>Taman Laut Olele</h1>
    </div>
    <div class="info-container">
        <div class="info">
            <h2>Informasi Tempat Wisata</h2>
            <ul>
                <li>Fasilitas+Harga:</li>
                <ul>
                    <li>1. Penginapan</li>
                    <li>2. Toilet</li>
                    <li>3. Area Parkir</li>
                    <li>4. Tempat Sampah</li>
                    <li>5. Perahu : Rp250.000</li>
                    <li>6. Alat Snorkeling : Rp50.000</li>
                    <li>7. Alat Diving : Rp250.000</li>
                </ul>
                <div class="separator"></div>
                <li>Harga Tiket: Umum/Gratis</li>
                <div class="separator"></div>
                <li>Jam Operasional: 24 jam</li>
            </ul>
        </div>
        <div class="address">
            <img src="olele 1.jpg" alt="Pantai Botubarani">
            <p><span>Alamat:</span></p>
            <p>C563+J3 Olele, Kabupaten Bone Bolango, Gorontalo</p>
            <p><a href="https://maps.app.goo.gl/D2EoQ7iYDNX3oyLd7">https://maps.app.goo.gl/D2EoQ7iYDNX3oyLd7</a></p>
            <p>Koordinat : 0°24'41.9"N 123°09'09.9"E</p>
        </div>
    </div>
    <div class="description">
        <h2>Deskripsi</h2>
        <p>Taman Laut Olele adalah sebuah taman laut dan kawasan wisata bahari yang berlokasi di Gorontalo, Indonesia. Taman Laut Olele memiliki keindahan pemandangan bawah laut yang unik. Tidak heran jika para penyelam dan penggemar fotografi bawah laut lokal maupun internasional memberikan julukan "The Hidden Paradise in Sulawesi" untuk taman laut ini. Taman Laut Olele kini menjadi incaran para wisatawan dan pecinta olahraga laut dari seluruh penjuru dunia.</p>
    </div>
    <div class="image-gallery">
        <img src="olele 2.jpg" alt="Image 1">
        <img src="olele 3.jpg" alt="Image 2">
    </div>
    <div class="centered-image">
        <div id="map" class="map"></div>
    </div>
</div>

<script>
    var locations = [
        ["Taman Laut Olele", 0.41177320689895003, 123.15273848650729],
    ];

    var map = L.map('map').setView([0.41177320689895003, 123.15273848650729], 12);
    mapLink = '<a href="http://openstreetmap.org">OpenStreetMap</a>';
    L.tileLayer(
        'http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '&copy; ' + mapLink + ' Contributors',
            maxZoom: 18,
        }).addTo(map);

    for (var i = 0; i < locations.length; i++) {
        marker = new L.marker([locations[i][1], locations[i][2]])
            .bindPopup(locations[i][0])
            .addTo(map);
    }
</script>

</body>
</html>

