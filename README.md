# DualNet: Robust Self-Supervised Stereo Matching with Pseudo-Label Supervision [AAAI 2025 (Oral)](https://ojs.aaai.org/index.php/AAAI/article/view/32882/35037)
Existing self-supervised stereo matching methods heavily rely on the **photo-metric consistency assumption**, which is vulnerable to natural disturbances, resulting in ambiguous supervision and inferior performance compared to the supervised ones. To relax the limitation of the photo-metric consistency assumption and even bypass this assumption, we propose a novel self-supervised framework named **DualNet**, which consists of two key steps: robust selfsupervised teacher learning and pseudo-label supervised student training. Specifcally, the teacher model is frst trained in a self-supervised manner with a focus on feature-metric consistency and data augmentation consistency. Then, the output of the teacher model is geometrically constrained to obtain high-quality pseudo labels. Benefting from these highquality pseudo labels, the student model can outperform its teacher model by a large margin. With the two well-designed steps, the proposed framework DualNet ranks **1st** among all self-supervised methods on multiple benchmarks, surprisingly even outperforming several supervised counterparts.

# Our Performance
our DualNet achieves **1st** performance among all self-supervised methods on KITTI 2012, KITTI 2015, Middlebury, and ETH3D benchmarks, even outperforming several supervised methods.
<img width="800" src="https://github.com/cocowy1/DualNet/blob/main/figs/teaser_1.png"/></div>

# The weak Photo-metric Consistency Assumption
Previous self-supervised stereo matching methods rely on the photo-metric consistency assumption, which assumes that the appearance of a point point photo-metric consistency assumption, which assumes that the appearance of a point in 3D space is color-invariant across different views. The hypothesis of photo-metric consistency is to maximize the similarity between the left image and the reconstructed left image after being warped from the right perspective. However, this foundational premise can be compromised by various real-world factors, such as low texture, occlusion, reflections, and illumination changes, as illustrated in below.
These challenges can confuse the self-supervision loss, leading to ambiguous supervision and ultimately resulting in inferior performance compared to supervised methods.
<img width="800" src="https://github.com/cocowy1/DualNet/blob/main/figs/color_constancy_v2.png"/></div>

# Overview
We present a self-supervised pipeline named DualNet, which can be divided into two key steps: (1) robust self-supervised teacher learning, which incorporates feature-metric and data augmentation consistency loss, and (2) pseudo-label supervised student training.
<img width="800" src="https://github.com/cocowy1/DualNet/blob/main/figs/overview_v1.png"/></div>
