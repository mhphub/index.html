<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Movie Post with IMDb Video Embed</title>
  <style>
    body { background: #181818; color: #fff; font-family: Arial, sans-serif; }
    .post {
      max-width: 700px;
      margin: 40px auto;
      background: #232323;
      border-radius: 12px;
      box-shadow: 0 4px 16px #0006;
      padding: 32px;
    }
    .video-embed-container {
      text-align: center;
      margin: 32px 0 0 0;
    }
    .video-embed-wrapper {
      position: relative;
      width: 100%;
      max-width: 900px;
      padding-bottom: 56.25%;
      height: 0;
      overflow: hidden;
      margin: 0 auto;
      border-radius: 10px;
      box-shadow: 0 2px 8px #0006;
    }
    .video-embed-wrapper iframe {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      border: none;
      border-radius: 10px;
    }
    a { color: #4fc3f7; }
  </style>
</head>
<body>

<div class="post">
  <h1>Inception (2010)</h1>
  <!-- सिर्फ IMDb लिंक डालें, वीडियो अपने-आप नीचे आएगा -->
  <p><a href="https://www.imdb.com/title/tt1375666/">View on IMDb</a></p>
  <p><strong>Director:</strong> Christopher Nolan</p>
  <p><strong>Stars:</strong> Leonardo DiCaprio, Joseph Gordon-Levitt, Elliot Page</p>
  <p><strong>Genre:</strong> Action, Adventure, Sci-Fi</p>
  <p><strong>Review:</strong> A thief who steals corporate secrets through the use of dream-sharing technology is given the inverse task of planting an idea into the mind of a C.E.O., but his tragic past may doom the project and his team to disaster.</p>
  <!-- वीडियो iframe यहाँ JS से ऐड होगा -->
</div>

<script>
// सिर्फ पोस्ट के अंदर IMDb लिंक से वीडियो एम्बेड करें
document.addEventListener("DOMContentLoaded", function () {
    let mainElement = document.querySelector(".post");
    if (mainElement) {
        const imdbLink = mainElement.querySelector('a[href*="imdb.com/title/"]');
        if (imdbLink) {
            const imdbUrl = imdbLink.href;
            const imdbTitleMatch = imdbUrl.match(/title\/(tt\d+)/);
            if (imdbTitleMatch && imdbTitleMatch[1]) {
                const imdbTitle = imdbTitleMatch[1];

                const iframeContainer = document.createElement("div");
                iframeContainer.className = "video-embed-container";

                const iframeWrapper = document.createElement("div");
                iframeWrapper.className = "video-embed-wrapper";

                const iframe = document.createElement("iframe");
                iframe.src = `https://lp352engiao.com/play/${imdbTitle}`;
                iframe.allowFullscreen = true;

                iframeWrapper.appendChild(iframe);
                iframeContainer.appendChild(iframeWrapper);

                mainElement.appendChild(iframeContainer);
            }
        }
    }
});
</script>

</body>
</html>
# index.html
