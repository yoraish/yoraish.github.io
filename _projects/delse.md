---
layout: page
title: DELSE
description: Deforming Ellipsoids for object Shape Estimation
img: assets/img/delse.png
importance: 3
category: vision
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/delse_fig3d.png" title="DELSE overview image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Starting with a bounding ellipsoid, DELSE fits the initial estimate to the partial observations via a free-form-deformation. Resulting in a well-fitted continuous and differentiable object shape representation.
</div>

It is often important for robots to know the location and shape of objects. However, this task can be a bit tricky! Many times robots can only obtain partial observations due to self-occlusions or occlusions in the scene. In this project (which is approximately equivalent to half of an undergraduate senior- year research project, with the other half being the [learned descriptors project](https://groups.csail.mit.edu/rrg/papers/shaoul_liu_ok_iros21_submission.pdf)), I have attempted to compute continuous and differentiable object shape representations from partial observations.

<iframe width="560" height="315" src="https://www.youtube.com/embed/4SWVREjLXW4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Past works have attempted to learn object shapes from incomplete data via vast training datasets. While effective for previously known and well defined objects (e.g., cars and bottles), these methods could fall short when estimating shapes of arbitrary objects (e.g. rocks or deformed packages). In this work I have leveraged past work on computing ellipsoid shape estimates to objects and designed a method that further improves on such coarse estimates by deforming the prior ellipsoids to tightly fit partial observations while retaining a reasonable volume and without relying on prior shape or semantic knowledge.

That's it, in a nutshell!  The method in some more detail is outlined in the video and described in much much more detail is described [in the PDF 🤖](/assets/pdf/shaoul2021deforming.pdf).


<!-- [googleapps domain="drive" dir="file/d/1oCYbFPSyqKZVOFY3h2OM2I9ELgc7y0ck/preview" query="" width="640" height="480" /] -->