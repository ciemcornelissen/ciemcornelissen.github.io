---
layout: about
title: about
permalink: /
subtitle: Researcher at <a href='https://www.ugent.be/ea/idlab/en'>IDLab</a>, Ghent University - imec

profile:
  align: right
  image: ciem_profile.png
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>IDLab, Department of Information Technology</p>
    <p>Ghent University - imec</p>
    <p>Ghent, Belgium</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I am a PhD researcher at [IDLab](https://www.ugent.be/ea/idlab/en), Department of Information Technology at Ghent University - imec, where I specialize in self-supervised representation learning and label-efficient world models for autonomous perception and control. My work spans multi-modal sensor fusion and latent-dynamics models that learn from observation sequences with limited manual or action labels.

My academic journey reflects a deliberate progression from fundamental science to applied AI. I completed my Bachelor's and Master's in Physics at Ghent University, where I developed strong analytical foundations and an aptitude for dissecting complex problems at their core. During my physics master's, elective courses in artificial intelligence sparked a passion that led me to pursue an Advanced Master's in Artificial Intelligence at KU Leuven (2023), where I specialized in deep learning, computer vision, and data science. This trajectory has uniquely positioned me to tackle the multi-modal representation learning challenges central to my PhD research.

My current research centers on two complementary questions: how to learn unified representations from heterogeneous sensors such as **RGB**, **LiDAR**, and **thermal** cameras, and how to learn planning-capable latent dynamics when action labels are scarce. I develop transformer-based predictive architectures that learn from unlabelled observations and can support perception tasks or goal-conditioned planning after limited task-specific supervision.

**Key Research Contributions:**

- Developed [**LaFreeWM**](/publications/#cornelissen2026lafreewm), a JEPA world model that infers discrete latent actions from unlabelled observation sequences before grounding its predictor for raw-action planning with a small labelled subset; the work also identifies a prediction-planning mismatch in which lower prediction error does not necessarily produce better control
- Developed **Le MuMo JEPA**, a multi-modal self-supervised framework that learns unified RGB-LiDAR-thermal representations through learnable fusion tokens, achieving strong performance-efficiency trade-offs on Waymo, nuScenes, and FLIR benchmarks (CVPR 2026 URVIS Workshop)
- Developed **LISA** (Light-Invariant Spectral Autoencoder), a domain-adversarial deep learning framework enabling robust spectral analysis under varying illumination conditions, part of an IoT-enabled robotic perception system
- Created **OHSLIC** (Online Hyperspectral Simple Linear Iterative Clustering), an efficient algorithm achieving real-time segmentation on resource-constrained edge devices through adaptive, on-device processing
- Co-authored research on computational fairness in adaptive neural networks, introducing resource allocation disparities as a novel dimension of algorithmic fairness and highlighting ethical considerations in efficiency-driven AI

My research includes the **LaFreeWM preprint** and peer-reviewed work in the **CVPR 2026 URVIS Workshop**, **IEEE Internet of Things Journal**, **IEEE/CVF Winter Conference on Applications of Computer Vision (WACV)**, and **Neural Computing and Applications**. Beyond research, I serve as a Teaching Assistant for the Reinforcement Learning course at Ghent University (2024-2026) and supervise master's thesis students on topics spanning multi-modal self-supervised learning, world models, and autonomous perception.

I am driven by a deep fascination with building AI systems that develop internal world models from multi-modal sensory data, enabling autonomous agents to perceive, predict, and act in complex environments. My research philosophy centers on designing self-supervised objectives and fusion architectures that learn generalisable representations, advancing both the theoretical foundations and practical deployment of multi-modal perception systems.
