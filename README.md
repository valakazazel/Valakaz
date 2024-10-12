 ```html
<!DOCTYPE html>
<html>
<head>
    <title>Ouvrir la caméra</title>
    <style>
        body {
            background-color: #f0f1f1;
            font-family: Phosphate, sans-serif;
            text-align: center;
            padding: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <h1>TEST BY HAMZA CHERKAOUI</h1>
    <button onclick="ouvrirCamera()">Ouvrir la caméra</button>
    
    <script>
        function ouvrirCamera() {
            navigator.mediaDevices.getUserMedia({ video: true })
            .then(function(stream) {
                var video = document.createElement('video');
                document.body.appendChild(video);
                video.srcObject = stream;
                video.play();
            })
            .catch(function(err) {
                console.log("Erreur : " + err);
            });
        }
    </script>
</body>
</html>
