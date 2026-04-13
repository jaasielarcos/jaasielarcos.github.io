# Sample workflow for building and deploying a Jekyll site to GitHub Pages
name: Deploy Jekyll with GitHub Pages dependencies preinstalled

on:layout: page
title: "PAGE-TITLE"
permalink: /URL-PATH
  # Runs on pushes targeting the default branch
  push:
    branches: ["main"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: ragdoll archers
        uses: ragdoll/archers
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
        with:
          source: ./
          destination: ./_site
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v5
        <Module>


<!-- Ultimate Game Stash file--> 
<!-- For the regularly updating doc go to https://docs.google.com/document/d/1_FmH3BlSBQI7FGgAQL59-ZPe8eCxs35wel6JUyVaG8Q/ -->



<!DOCTYPE html><html lang="en-us"><head>
<script src="https://cdn.jsdelivr.net/gh/laparda14/Ragdoll-archers@62504c9570ea720c6367e7debe1e110c68f77c2d/vs/gameloader-helper.js"></script>
<meta charset="utf-8">
<script src=""></script>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<title>Ragdoll Archers</title>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/bubbls/ruffle@04dd5345a30d6ebf4b0e2cc385568750cd56ed5a/styyyle.css">
<body>
  
</div>
<div id="unity-container" class="unity-desktop">
<canvas id="unity-canvas"></canvas>
</div>
<div id="loading-cover">
<div id="unity-loading-bar">
<div id="unity-logo"><img src="logo.jpeg"></div>
<div class="progress-spinner-container">
<div class="spinner-left"><img src="spinner.png"></div>
<div id="unity-progress-bar-empty">
<div id="unity-progress-bar-full"></div>
</div>
<div class="spinner-right"><img src="spinner.png"></div>
</div>
</div>
</div>
<script>
    const buildUrl = "Build";
    const loaderUrl = "https://cdn.jsdelivr.net/gh/bubbls/ruffle@7117cc5006472d782b65d96abd375597d6273242/v11121212.js";
const config = {
  dataUrl: "https://cdn.jsdelivr.net/gh/bubbls/ruffle@04dd5345a30d6ebf4b0e2cc385568750cd56ed5a/6697b6deba8b617c67b69c55dcd07cb1.data.unityweb",
  frameworkUrl: "https://cdn.jsdelivr.net/gh/bubbls/ruffle@04dd5345a30d6ebf4b0e2cc385568750cd56ed5a/0be3c3ee7115b26e1ae28e643afdf1f2.js.unityweb",
  codeUrl: "https://cdn.jsdelivr.net/gh/bubbls/ruffle@04dd5345a30d6ebf4b0e2cc385568750cd56ed5a/b3397c29f6878557c1c614cbf9e196ea.wasm.unityweb",
  streamingAssetsUrl: "StreamingAssets",
  companyName: "Ericetto",
  productName: "Ragdoll Archers",
  productVersion: "0.1",
};


    const container = document.querySelector("#unity-container");
    const canvas = document.querySelector("#unity-canvas");
    const loadingCover = document.querySelector("#loading-cover");
    const progressBarEmpty = document.querySelector("#unity-progress-bar-empty");
    const progressBarFull = document.querySelector("#unity-progress-bar-full");

    if (/iPhone|iPad|iPod|Android/i.test(navigator.userAgent)) {
      container.className = "unity-mobile";
    }
    
    loadingCover.style.display = "";

    const unityLoader = document.createElement("script");
    unityLoader.src = loaderUrl;
    unityLoader.onload = () => {
      createUnityInstance(canvas, config, (progress) => {
        progressBarEmpty.style.display = "";
        progressBarFull.style.width = `${100 * progress}%`;
      }).then((unityInstance) => {
        window.unityInstance = unityInstance;
        loadingCover.style.display = "none";
      }).catch((message) => {
        alert(message);
      });
    };
    document.body.appendChild(unityLoader);

    document.addEventListener("pointerdown", () => {
      container.focus();
      window.focus();
      canvas.focus();
    });

  </script>
</body></html>
