---
layout: page
card_title: imagenet-shift
title: ImageNet-Cartoon & ImageNet-Drawing
description: Two domain shift datasets for ImageNet.
img: assets/img/imagenet-shift/imagenet-shift.png
importance: 1
category: machine learning
github: https://github.com/oberman-lab/imagenet-shift
---

<p align="justify">
Benchmarking the robustness to distribution shifts traditionally relies on dataset collection which is typically laborious and expensive, in particular for datasets with a large number of classes like ImageNet. An exception to this procedure is ImageNet-C, a dataset created by applying common real-world corruptions at different levels of intensity to the (clean) ImageNet images. Inspired by this work, we introduce <b>ImageNet-Cartoon</b> and <b>ImageNetDrawing</b>, two datasets constructed by converting ImageNet images into cartoons and colored pencil drawings, using a GAN framework [1] and simple image processing [2], respectively. We show that the accuracy of pretrained ImageNet models decreases significantly on the proposed datasets.

</p>

### ImageNet-Cartoon
<p align="justify">
Images are taken from the ImageNet dataset and the transformed into cartoon using the GAN framework proposed by [1].
</p>

<div class="row mx-1 justify-content-sm-center">
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_400_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1"  width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_451_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_507_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_11705_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_38951_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39303_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39505_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39707_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
</div>
<div class="row mx-1 justify-content-sm-center">
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_400_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1"  width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_451_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_507_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_11705_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_38951_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39303_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39505_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39707_ImageNet-Cartoon.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
</div>
<div class="caption">
    Several examples of ImageNet images (top) and their respective ImageNet-Cartoon (bottom).
</div>



### ImageNet-Drawing
Images are taken from the ImageNet dataset and the transformed into colored pencil drawings using the simple image processing described in [2].

<div class="row mx-1 justify-content-sm-center">
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_400_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1"  width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_451_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_507_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_11705_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_38951_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39303_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39505_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39707_ImageNet.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
</div>
<div class="row mx-1 justify-content-sm-center">
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_400_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1"  width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_451_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-3 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_507_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_11705_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_38951_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39303_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39505_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
    <div class="col- mt-0 mt-md-1 px-1">
        {% include figure.html path="assets/img/imagenet-shift/examples/id_39707_ImageNet-Drawing.JPEG" title="example image" class="img-fluid rounded z-depth-1" width="105px"%}
    </div>
</div>
<div class="caption">
    Several examples of ImageNet images (top) and their respective ImageNet-Drawing (bottom).
</div>

### Access
We uploaded the dataset on [Zenodo](https://zenodo.org/record/6801109), as well as the source code on [Github](https://github.com/oberman-lab/imagenet-shift) to generate the two datasets.

### License
We released the data with the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode).

### References

[1] Wang, X. and Yu, J. Learning to cartoonize using white-box cartoon representations. In _Proceedings of the IEEE/CVF
Conference on Computer Vision and Pattern Recognition (CVPR)_, June 2020.

[2] Lu, C., Xu, L., and Jia, J. Combining Sketch and Tone for Pencil Drawing Production. In Asente, P. and Grimm, C.
(eds.), _International Symposium on Non-Photorealistic Animation and Rendering_. The Eurographics Association, 2012. ISBN 978-3-905673-90-6. doi: 10.2312/PE/NPAR/NPAR12/065-073.

### Citation

You can see the full paper [here](https://openreview.net/pdf?id=YlAUXhjwaQt). Please cite as

    @inproceedings{salvador2022imagenetcartoon,
        title={ImageNet-Cartoon and ImageNet-Drawing: two domain shift datasets for ImageNet},
        author={Tiago Salvador and Adam M Oberman},
        booktitle={ICML 2022 Shift Happens Workshop},
        year={2022},
        url={https://openreview.net/forum?id=YlAUXhjwaQt}
    }