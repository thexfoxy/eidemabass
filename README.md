<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>عیدی روز مبعث</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-image: url('https://s6.uupload.ir/files/r_vgge.jpg'); /* لینک تصویر پس‌زمینه را اینجا قرار دهید */
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      text-align: center;
      background-color: rgba(255, 255, 255, 0.8); /* پس‌زمینه کمی شفاف برای خوانایی بهتر */
      padding: 40px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      width: 300px;
    }

    h1 {
      color: #333;
      font-size: 24px;
    }

    .button {
      background-color: #4CAF50;
      color: white;
      padding: 15px 32px;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
      border-radius: 5px;
      margin-top: 20px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .button:hover {
      background-color: #45a049;
    }

    p {
      font-size: 16px;
      color: #555;
    }

    #location {
      font-size: 18px;
      margin-top: 20px;
      font-weight: bold;
      color: #333;
    }
  </style>
</head>
<body>
<div class="container">
  <h1>برای دریافت عیدی کلیک کنید</h1>
  <a href="javascript:void(0);" class="button" onclick="getLocation()">دریافت عیدی</a>
  <p id="location"></p>
</div>

<script>
  function getLocation() {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(showPosition, showError);
    } else {
      alert("Your browser does not support geolocation.");
    }
  }

  function showPosition(position) {
    var lat = position.coords.latitude;
    var lon = position.coords.longitude;
    document.getElementById("location").innerHTML = "Latitude: " + lat + "<br>Longitude: " + lon;
  }

  function showError(error) {
    switch(error.code) {
      case error.PERMISSION_DENIED:
        alert("User denied the request for geolocation.");
        break;
      case error.POSITION_UNAVAILABLE:
        alert("Location information is unavailable.");
        break;
      case error.TIMEOUT:
        alert("The request to get user location timed out.");
        break;
      case error.UNKNOWN_ERROR:
        alert("An unknown error occurred.");
        break;
    }
  }
</script>
</body>
</html>
