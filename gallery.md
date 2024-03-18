---
layout: single
author_profile: true
permalink: /gallery/
title: Gallery
tags: [gallery]
modified: 2024-03-18
comments: false
# gallery:
#   - url: /assets/images/aa.jpg
#     image_path: /assets/images/aa.jpg
#     alt: "Placeholder for image 1"
#     title: ""
#   - url: /assets/images/bb.jpg
#     image_path: /assets/images/bb.jpg
#     alt: "Placeholder for image 2"
#     title: ""
#   - url: /assets/images/cc.jpg
#     image_path: /assets/images/cc.jpg
#     alt: "Placeholder for image 3"
#     title: ""  
#   - url: /assets/images/dd.jpg
#     image_path: /assets/images/dd.jpg
#     alt: "Placeholder for image 4"
#     title: ""
#   - url: /assets/images/ee.jpg
#     image_path: /assets/images/ee.jpg
#     alt: "Placeholder for image 5"
#     title: ""      
#   - url: /assets/images/ImagesPost5/Series6-2.jpg
#     image_path: /assets/images/ImagesPost5/Series6-2.jpg
#     alt: "Placeholder for image 6"
#     title: ""   
---
<!-- {% raw %}
<div class="gallery">
  <img src="/assets/images/aa.jpg" alt="Placeholder for image 1" width="500" height="600">
  <img src="/assets/images/bb.jpg" alt="Placeholder for image 2" width="500" height="600">
  <img src="/assets/images/cc.jpg" alt="Placeholder for image 3" width="500" height="600">
  <img src="/assets/images/dd.jpg" alt="Placeholder for image 4" width="500" height="600">
  <img src="/assets/images/ee.jpg" alt="Placeholder for image 5" width="500" height="600">
  <img src="/assets/images/ImagesPost5/Series6-2.jpg" alt="Placeholder for image 6" width="500" height="600">
</div>
{% endraw %} -->
{% raw %}
<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 10px;
}
.gallery img {
  width: 100%;
  height: auto;
}
</style>

<div class="gallery">
  <img src="/assets/images/aa.jpg" alt="Placeholder for image 1">
  <img src="/assets/images/bb.jpg" alt="Placeholder for image 2">
  <img src="/assets/images/cc.jpg" alt="Placeholder for image 3">
  <img src="/assets/images/dd.jpg" alt="Placeholder for image 4">
  <img src="/assets/images/ee.jpg" alt="Placeholder for image 5">
  <img src="/assets/images/ImagesPost5/Series6-2.jpg" alt="Placeholder for image 6">
</div>
{% endraw %}

<!-- {% include gallery caption="This is a sample gallery with **Markdown support**." %} -->