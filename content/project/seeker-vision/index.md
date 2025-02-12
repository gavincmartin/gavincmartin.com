+++
# Project title.
title = "Seeker Vision"

# Date this page was created.
date = 2019-05-29T12:00:00

# Project summary to display on homepage.
summary = "A NASA-funded machine learning project for autonomous vision-based navigation in space. Flew on the Seeker CubeSat in 2019."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
# tags = ["Deep Learning"]

# Optional external URL for project (replaces project detail page).
# external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides = ""

# Links (optional).
# url_pdf = ""
# url_slides = ""
# url_video = ""
# url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# links = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Credit: NASA"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

# Seeker Vision

I led a team of student researchers and engineers in the Texas Spacecraft Laboratory on the Seeker Vision project—an effort to give NASA’s Seeker spacecraft the ability to detect, identify, and localize another spacecraft (Cygnus) in orbit using nothing but a low-cost camera and CPU. We adapted deep neural networks to the space environment and integrated our machine learning models with flight software, giving the spacecraft new autonomous capabilities.

<center>{{< figure src="seeker-deep-space-tracking.gif" title="Tracking Cygnus against deep space (easier)" >}}</center>

<center>{{< figure src="seeker-earth-tracking.gif" title="Tracking Cygnus against a noisy Earth backdrop (more difficult)" >}}</center>

## Mission Summary & Seeker Vision Overview

Seeker was a NASA Johnson Space Center (JSC) program that aimed to demonstrate the core capabilities required for safe external robotic free-flyer inspection of crewed space vehicles. External inspection of crewed space vehicles is a crucial next-step in manned space exploration.

<center>{{< figure src="seeker-kenobi.png" title="Seeker (left) & its 'translator' Kenobi (right). Credit: NASA" >}}</center>

The Texas Spacecraft Laboratory (TSL), with UT Aerospace Engineering and Engineering Mechanics professor Dr. Maruthi Akella serving as Principal Investigator, was funded to develop a vision system for the Seeker-1 technology demonstration mission that launched in April 2019. Seeker-1 was a 3U CubeSat deployed from an Orbital ATK Enhanced Cygnus ISS resupply spacecraft following the completion of its resupply mission. The Seeker-1 CubeSat performed a 60-minute mission consisting of proximity operations around the Cygnus spacecraft. The TSL-developed vision system was isolated from all other sensors onboard the spacecraft, using only a commercially available camera and state-of-the-art computer vision algorithms to detect the Cygnus spacecraft (or its lack thereof) and compute its relative bearing in a variety of lighting conditions, orientations, and background environments. The measurements taken by the intelligent camera system were then used in real-time in the guidance, navigation, and control of the Seeker-1 CubeSat.

## Vision System Development Highlights

### Computer Vision Software Overview

NASA asked us to deliver a computer vision system capable of detecting Cygnus and
producing relative azimuth & elevation estimates at 1 Hz. With only a weak computer (and no GPU), this was no trivial task.

And, the space environment presents many difficulties with respect to computer vision:

- Clouds and Earth generate complex noise patterns
- Lighting is inconsistent and can easily blind the camera
  or illuminate only half an object
- Low computing power and time constraints can eliminate many solutions viable for Earth-based systems

Additionally, our target spacecraft, Cygnus, was considered "non-cooperative," meaning that has no visual markers or reflectors that make computer vision easier, and does not actively communicate its position during the mission. Interaction with non-cooperative targets in space is difficult but highly desirable.

We met our mission need for robustness and performance by training and tuning models built from Google's MobileNet SSD v1 architecture. The lightweight object detector proved resilient and speedy in simulations and extensive hardware-in-the-loop testing.

### Synthetic Image Generation

While training data for terrestrial vehicles is relatively easy to gather (though painstaking to label), imagery for training autonomous spacecraft is rather limited. Moreover, we needed images that exhaustively sampled backgrounds conditions and orientations. We immediately identified synthetic imagery as a critical mission need and developed software to create high-fidelity simulated images for training.

Using Unreal Engine and Microsoft's AirSim, we were able to script the generation of thousands of diverse images to bolster our datasets and dramatically improve our training results.

<center>{{< figure src="simulated-cygnus.png" title="A synthetically-generated image of Cygnus (1 / 2)" >}}</center>

<center>{{< figure src="simulated-cygnus-2.png" title="A synthetically-generated image of Cygnus (2 / 2)" >}}</center>

For each simulated image, we could immediately generate ground-truth data to use for both training and validation. This helped in past efforts for relative bearing estimation and will aid in future efforts towards full 6-DOF pose estimation.

### Neural Network Results

After iterative trainings and hyperparameter tuning, we developed a capable object detector.

<center>{{< figure src="results_histogram.png" title="Test set results: Cygnus detection probability in positive and negative images (where a bimodal distribution is good)" >}}</center>

| Metric                           | Validation Set Average | Testing Set Average |
| -------------------------------- | ---------------------- | ------------------- |
| Detection Rate                   | 0.99                   | 0.965               |
| True Negative Rate               | 0.953                  | 0.973               |
| False Positive Rate              | 0.047                  | 0.027               |
| False Alarm Rate                 | 0.034                  | 0.02                |
| False Negative Rate              | 0.01                   | 0.035               |
| Accuracy                         | 0.974                  | 0.969               |
| Precision                        | 0.966                  | 0.98                |
| F1                               | 0.978                  | 0.972               |
| Matthews Correlation Coefficient | 0.948                  | 0.936               |
| Jaccard Coefficient              | 0.89                   | 0.888               |

<center>{{< figure src="example-cygnus-detection.png" title="An example Cygnus detection" >}}</center>

## Delivery & Deployment

In May 2018, the TSL delivered a vision system to JSC capable of computing relative azimuth and elevation at a solution rate of 3-4 Hz. In August 2018, this vision system was selected for flight over competing systems after testing proved it to be the most robust solution available. **It was integrated into the final Seeker-1 CubeSat, launched on Cygnus NG-11 in April 2019 and was deployed after a Cygnus re-supply in September 2019**.

## Longhorn Research Poster Session

We presented our research at UT Research Week's poster session in April 2019 and won the 1st-place audience favorite award. You can find our poster [here](seeker_utrw_poster.pdf).

## Follow-On Work

Thanks to the success of the delivered system, JSC chose to fund continued research in order to develop a second-generation system capable of computing relative pose as an extension of the current relative bearing capabilities.

Using lessons learned from this mission, we architected a cutting-edge ML pipeline
which aimed to: (1) generate synthetic training data with a high degree of photorealism,
(2) stitch together real and synthetic data to produce diverse training
datasets, (3) provision cloud resources dedicated to neural network training, (4)
evaluate trained models against real and synthetic data, and (5) support rapid iteration on 1-4.

<center>{{< figure src="tsl-ml-pipeline.png" title="An ML pipeline built for rapid training and iteration" >}}</center>

Subsequent generations of students at UT have built on our vision and have used this pipeline to improve model performance, tailor models to other types of spacecraft, and even perform full 6-DOF pose estimation on a CubeSat flight computer.

For more information on the excellent work of these students, check out _[A Pipeline for Vision-Based On-Orbit Proximity Operations Using Deep Learning and Synthetic Imagery](https://arxiv.org/pdf/2101.05661.pdf)_ and _[Flight-Ready, Non-Cooperative Spacecraft Pose Estimation Using Monocular Imagery](https://arxiv.org/pdf/2101.09553.pdf)_.
