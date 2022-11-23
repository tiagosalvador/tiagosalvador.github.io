---
layout: page
title: FairCal
card_title: FairCal
description: Fairness Calibration for Face Verification
img: assets/img/faircal/faircal.png
importance: 2
category: machine learning
github: https://github.com/tiagosalvador/faircal
---

Despite being widely used, face recognition models suffer from bias: the probability of a false positive (incorrect face match) strongly depends on sensitive attributes such as the ethnicity of the face. As a result, these models can disproportionately and negatively impact minority groups, particularly when used by law enforcement.

The majority of bias reduction methods have several drawbacks: they use an end-to-end retraining approach, may not be feasible due to privacy issues, and often reduce accuracy. An alternative approach is post-processing methods that build fairer decision classifiers using the features of pre-trained models, thus avoiding the cost of retraining. However, they still have drawbacks: they reduce accuracy (AGENDA, PASS, FTC), or require retuning for different false positive rates (FSN).

In this work, we introduce the Fairness Calibration method, <b>FairCal</b>, a post-training approach that simultaneously:
<style> ol {list-style: none;} ol>li:before {content: attr(seq) " ";} </style>
<ol>
  <li seq="(i)">increases model <b>accuracy</b> (improving the state-of-the-art);</li>
  <li seq="(ii)">produces <b>fairly-calibrated</b> probabilities;</li>
  <li seq="(iii)">significantly reduces the gap in the <b>false positive rates</b>;</li>
  <li seq="(iv)">does not require knowledge of the <b>sensitive attribute</b> (group identity such as race, ethnicity, etc.);</li>
  <li seq="(v)">does not require <b>retraining</b>, training an additional model, or retuning.</li>
</ol>
We apply it to the task of Face Verification, and obtain state-of-the-art results with all the above advantages. We do so by applying a post-hoc calibration method to pseudo-groups formed by unsupervised clustering.

<div class="row justify-content-sm-center">
    <div class="col-sm-12 mt-3 mt-md-0">        
        {% include figure.html path="assets/img/faircal/rfw_facenet-webface_thr_vs_fpr.png" title="example image" class="img-fluid rounded z-depth-1"%}
    </div>
</div>
<div class="caption">
    (Lines closer together is better for fairness) Illustration of improved fairness / reduction in bias, as measured by the FPRs evaluated on intra-ethnicity pairs on the RFW dataset with the FaceNet (Webface) feature model. At a Global FPR of 5% using the baseline method Black people are 15X more likely to false match than white people. Our method reduces this to 1.2X (while SOTA for post-hoc methods is 1.7X).
</div>


### Fairness and Bias in Face Verification

The Face Verification problem consists in given two images, decide if it is a genuine/imposter pair.

<div class="row justify-content-sm-center">
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/faircal/images_faces/bart_simpson_1.jpeg" title="example image" class="img-fluid rounded z-depth-1" width="100px"%}
    </div>
    <div class="col-sm-2 mt-3 mt-md-0">        
        {% include figure.html path="assets/img/faircal/images_faces/bart_simpson_2.png" title="example image" class="img-fluid rounded z-depth-1" width="100px"%}
    </div>
    <div class="col-sm-2 mt-3 mt-md-0">
    </div>
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/faircal/images_faces/bart_simpson_1.jpeg" title="example image" class="img-fluid rounded z-depth-1" width="100px"%}
    </div>
    <div class="col-sm-2 mt-3 mt-md-0">
        {% include figure.html path="assets/img/faircal/images_faces/homer_simpson.jpeg" title="example image" class="img-fluid rounded z-depth-1" width="100px"%}
    </div>
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-2 mt-3 mt-md-0">  Genuine Pair </div>
    <div class="col-sm-4 mt-3 mt-md-0"> </div>
    <div class="col-sm-2 mt-3 mt-md-0"> Imposter Pair </div>
</div>

Chouldechova (2017) showed that maximum two of the following three conditions can be satisfied:

<ol>
  <li seq="1)"><b>Fairness Calibration</b>, i.e., calibrated fairly for different subgroups:</li>
$$
\mathbb{P}_{\boldsymbol{x}_1,\boldsymbol{x}_2 \sim \mathcal{G}_1}(Y=1\mid \widehat{C}=c) = \mathbb{P}_{\boldsymbol{x}_1,\boldsymbol{x}_2 \sim \mathcal{G}_2}(Y=1\mid \widehat{C}=c) = c
$$

<li seq="2)"><b>Predictive Equality</b>, i.e., equal False Positive Rates (FPRs) across different subgroups:</li>

$$
\mathbb{P}_{(\boldsymbol{x}_1,\boldsymbol{x}_2) \sim \mathcal{G}_1}(\widehat{Y}=1\mid Y=0) = \mathbb{P}_{(\boldsymbol{x}_1,\boldsymbol{x}_2) \sim\mathcal{G}_2}(\widehat{Y}=1\mid Y=0)
$$

  <li seq="3)"><b>Equal Opportunity</b>, i.e., equal False Negative Rates across different subgroups:</li>

$$
\mathbb{P}_{(\boldsymbol{x}_1,\boldsymbol{x}_2) \sim \mathcal{G}_1}(\widehat{Y}=0\mid Y=1) = \mathbb{P}_{(\boldsymbol{x}_1,\boldsymbol{x}_2) \sim \mathcal{G}_2}(\widehat{Y}=0\mid Y=1)
$$
</ol>

In the particular context of policing, <b>predictive equality</b> is considered more important than equal opportunity, as false positive errors (false arrests) risk causing significant harm, especially to members of subgroups already at disproportionate risk for police scrutiny or violence. Hence we choose to omit equal opportunity as our goal and note that no prior method has targeted <b>Fairness Calibration</b>. <b>Predictive equality</b> is measured by comparing the FPR on each subgroup at one global FPR.

### Goals and Related Work

Work on bias mitigation for deep Face Verification models can be divided into two main camps:
<ol>
  <li seq="(i)">methods that let a model learn less-biased representations during training, and</li>
  <li seq="(ii)">post-processing approaches that attempt to remove bias <i>after</i> a model is trained.</li>
</ol>

Our work focuses on (ii) post-hoc methods.

<div class="row justify-content-sm-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.html path="assets/img/faircal/table.png" title="example image" class="img-fluid rounded z-depth-1"%}
    </div>
</div>
<div class="caption">
    Comparison of desirable features of the different post-hoc fairness methods for face verification.
</div>

## Baseline Approach

Given a trained neural network $$f$$ that encodes an image $$\boldsymbol{x}$$ into an embedding $$\boldsymbol{z} = f(\boldsymbol{x})$$, the baseline classifier for the face verification problem is the following.

1. 1) Given an image pair $$(\boldsymbol{x}_1,\boldsymbol{x}_2)$$: compute the feature embedding pair $$(\boldsymbol{z}_1, \boldsymbol{z}_2)$$.
2. 2) Compute the cosine similarity score $$s(\boldsymbol{x}_1,\boldsymbol{x}_2)=\frac{\boldsymbol{z}_1^T \boldsymbol{z}_2}{\|\boldsymbol{z}_1\| \|\boldsymbol{z}_2\|}$$.
3. 3) Given a predefined threshold $$s_{\rm{thr}}: s(\boldsymbol{x}_1,\boldsymbol{x}_2) > s_{\rm{thr}} \implies$$ genuine pair!

### FairCal

We build our proposed method <b>FairCal</b> based on two main ideas:
1. 1) Use the feature vector to define population subgroups;
2. 2) Use post-hoc calibration methods that convert cosine similarity scores into probabilities of genuine (or imposter) pair.

##### <u>Calibration stage</u>
Let $$\mathcal{Z}^{\rm{cal}}$$ denote the feature embeddings of a set of face images.

1. 1) Apply $$K$$-means algorithm to $$\mathcal{Z}^{\rm{cal}}$$, partitioning the embedding space into $$K$$ clusters $$\mathcal{Z}_1,\ldots,\mathcal{Z}_K$$

2. 2) Form the $$K$$ calibration sets of cosine similarity scores:

$$
        S^{\rm{cal}}_k = \left\{
        s(\boldsymbol{x}_1,\boldsymbol{x}_2):  f(\boldsymbol{x}_1) \in \mathcal{Z}_k \text{ or } f(\boldsymbol{x}_2) \in \mathcal{Z}_k
        \right\}, \quad k = 1, \dots, K
$$

3. 3) For $$k=1,\ldots,K$$ estimate the calibration map $$\mu_k$$ that calibrates the scores:

$$
    \mu_k (s(\boldsymbol{x}_1,\boldsymbol{x}_2)) = \mathbb{P}[Y=1\mid S=s, f(\boldsymbol{x}_1) \in \mathcal{Z}_k \text{ or } f(\boldsymbol{x}_2) \in \mathcal{Z}_k]
$$

For <b>FairCal</b> we chose Beta Calibration (Kull et al, 2017) as the post-hoc calibration method but experiments show similar performance with other calibration methods.
    
##### <u>Test stage</u>

1. 1) Given an image pair ($$\boldsymbol{x}_1$$, $$\boldsymbol{x}_2$$), compute ($$z_1$$, $$z_2$$), and the cluster of each image feature: $$k_1$$ and $$k_2$$
2. 2) The model's confidence $$c$$ in it being a genuine pair is:

$$
c(\boldsymbol{x}_1,\boldsymbol{x}_2) =  \theta\ \mu_{k_1}(s(\boldsymbol{x}_1,\boldsymbol{x}_2))\ + (1-\theta)\  \mu_{k_2}(s(\boldsymbol{x}_1,\boldsymbol{x}_2))
$$

where $$\theta = \frac{\|S^{\rm{cal}}_{k_1}\|}{\|S^{\rm{cal}}_{k_1}\|+\|S^{\rm{cal}}_{k_2}\|}$$ is the relative population fraction of the two clusters.

3. 3) Given a predefined threshold $$c_{\rm{thr}}: c(\boldsymbol{x}_1,\boldsymbol{x}_2) > c_{\rm{thr}} \implies$$ genuine pair!

<div class="row justify-content-sm-center">
    <div class="col-sm-12 mt-3 mt-md-0">        
        {% include figure.html path="assets/img/faircal/diagram_faircal.png" title="example image" class="img-fluid rounded z-depth-1"%}
    </div>
</div>
<div class="caption">
    Illustrative diagram of our <b>FairCal</b> method. Highlighted in red are the components that distinguish it from the baseline approach.
</div>

### Results

Our results show that among post hoc calibration methods,
1. 1) <b>FairCal</b> has the <u>best Fairness Calibration</u>.
2. 2) <b>FairCal</b> has the <u>best Predictive Equality</u>, i.e., equal FPRs,
3. 3) <b>FairCal</b> has the <u>best global accuracy</u>,
4. 4) <b>FairCal</b> <u>does not require the sensitive attribute</u> and outperforms methods that use this knowledge,
5. 5) <b>FairCal</b> <u>does not require retraining</u> of the classifier, or any additional training.

### Unsupervised Clusters

In order to not rely on the sensitive attribute like the Oracle method, our <b>FairCal</b> method uses unsupervised clusters computed with the K-means algorithm based on the feature embeddings of the images. We found them to have semantic meaning.

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/faircal/cluster_visualization/facenet_fold5_cluster_38.png" title="example image" class="img-fluid rounded z-depth-1"%}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">        
        {% include figure.html path="assets/img/faircal/cluster_visualization/facenet_fold5_cluster_4.png" title="example image" class="img-fluid rounded z-depth-1"%}
    </div>
</div>
<div class="caption">
   Examples of clusters obtained with the K-means algorithm (K=100) on the RFW dataset based on the feature embeddings computed with the FaceNet model. The left cluster is predominantly composed of Caucasian Blonde Women, while the right cluster is composed of Indian Men with Moustaches.
</div>

### Citation

You can see the full paper [here](https://openreview.net/pdf?id=nRj0NcmSuxb). Please cite as

    @inproceedings{salvador2022faircal,
        title={FairCal: Fairness Calibration for Face Verification},
        author={Tiago Salvador and Stephanie Cairns and Vikram Voleti and Noah Marshall and Adam M Oberman},
        booktitle={International Conference on Learning Representations},
        year={2022},
        url={https://openreview.net/forum?id=nRj0NcmSuxb}
    }