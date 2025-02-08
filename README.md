<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacked!</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background: black;
            color: green;
            text-align: center;
            font-family: 'Courier New', Courier, monospace;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        #code, #announcement, #image, #by-text, #video-container {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        #code {
            font-size: 1.5em;
            white-space: pre-wrap;
            text-align: left;
        }
        #announcement {
            font-size: 2em;
            font-weight: bold;
            color: red;
        }
        #image img {
            max-width: 100vw;
            max-height: 100vh;
        }
        #by-text {
            font-size: 3em;
            font-weight: bold;
            color: red;
        }
        iframe {
            width: 100vw;
            height: 100vh;
            border: none;
        }
    </style>
</head>
<body>
    <div id="code"></div>
    <div id="announcement">I WANT TO ANNOUNCE THAT</div>
    <div id="image">
        <img src="https://raw.githubusercontent.com/EclipseIce/Hack/refs/heads/main/pdo5kmjuy3661.webp" alt="Hacked Image">
    </div>
    <div id="by-text">BY AZURE CLOUD</div>
    <div id="video-container">
      <iframe src="https://raw.githubusercontent.com/EclipseIce/Hack/main/images/202502070908.mp4" allowfullscreen></iframe>
    </div>
    <audio id="typing-sound" src="keyboard-typing-5997.mp3"></audio>
    <audio id="laugh-sound" src="your-laugh-sound.mp3"></audio>
    
    <script>
        function goFullscreen() {
            let elem = document.documentElement;
            if (elem.requestFullscreen) {
                elem.requestFullscreen();
            } else if (elem.mozRequestFullScreen) { 
                elem.mozRequestFullScreen();
            } else if (elem.webkitRequestFullscreen) { 
                elem.webkitRequestFullscreen();
            } else if (elem.msRequestFullscreen) { 
                elem.msRequestFullscreen();
            }
        }
        
        function typeEffect(element, text, speed, callback) {
            let i = 0;
            let audio = document.getElementById('typing-sound');
            audio.play();
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                } else {
                    audio.pause();
                    if (callback) callback();
                }
            }
            type();
        }
        
        function sequence() {
            goFullscreen();
            let codeElement = document.getElementById('code');
            let announcementElement = document.getElementById('announcement');
            let codeText = "🖥 SYSTEM ERROR: Unauthorized Access Detected!\n\n🔄 Restarting system…\n\n🟡 Verifying identity... [FAILED]\n\n🔴 Security Breach! Initiating lockdown…";
            
            codeElement.style.display = 'block';
            typeEffect(codeElement, codeText, 75, () => {
                setTimeout(() => {
                    codeElement.style.display = 'none';
                    announcementElement.style.display = 'block';
                    setTimeout(() => {
                        announcementElement.style.display = 'none';
                        document.getElementById('image').style.display = 'block';
                        document.getElementById('laugh-sound').play();
                        setTimeout(() => {
                            document.getElementById('image').style.display = 'none';
                            document.getElementById('by-text').style.display = 'block';
                            setTimeout(() => {
                                document.getElementById('by-text').style.display = 'none';
                                document.getElementById('video-container').style.display = 'block';
                            }, 2000);
                        }, 3000);
                    }, 2000);
                }, 3000);
            });
        }
        
        window.onload = sequence;
    </script>
</body>
</html>
