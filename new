<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Geolocation and Time Updater</title>
    <script>
        function updateGeolocationAndTime() {
            if ("geolocation" in navigator) {
                navigator.geolocation.getCurrentPosition(function(position) {
                    var geoValue = position.coords.latitude + ", " + position.coords.longitude;
                    var currentTime = new Date().toISOString();

                    // Post the geolocation and time data to the parent form
                    window.parent.postMessage({
                        geoValue: geoValue,
                        currentTime: currentTime
                    }, '*');
                }, function(error) {
                    console.error("Geolocation error:", error.message);
                });
            } else {
                console.error("Geolocation is not supported by this browser.");
            }
        }

        // Update geolocation and time when the iframe loads
        window.addEventListener('load', updateGeolocationAndTime);
    </script>
</head>
<body>
    <p>Updating geolocation and time...</p>
</body>
</html>
