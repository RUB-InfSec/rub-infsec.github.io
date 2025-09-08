---
title: Infrared Perturbations
feature_text: |
  # Targeted Physical Evasion Attacks in the Near-Infrared Domain
excerpt: "Targeted Physical Evasion Attacks in the Near-Infrared Domain (NDSS'26) exploit the visibility of infrared-light to CMOS camera sensors and invisibility to the human eye to manipulate predictions of machine learning systems."
aside: false
paperlink: true
sidebar: "index"
---

### Physical Evasion Attacks Against Traffic Sign Recognition Systems

Deep neural networks, which are widely used in traffic sign recognition systems, are vulnerable to malicious inputs known as adversarial examples. These attacks can have serious consequences in safety-critical applications, such as autonomous vehicles, by causing misclassifications of traffic signs. For example, the misclassification of a stop sign as a speed limit sign or vice-versa by an autonomous vehicle poses a significant safety hazard. Therefore, it is crucial to develop robust defense mechanisms to protect these systems against such attacks. There are various types of physical types, including:

1. **Adversarial Patches**: These are static, visible perturbations that can be applied to traffic signs. They have been shown to be effective in causing misclassifications, but they leave a visible trace and are limited in their degrees of freedom. Examples include stickers, snow, or shadows that mimic plausible scenarios.

2. **Projector-based Attacks**: These attacks exploit the full RGB color space by projecting arbitrary images onto a target with close to pixel-wise precision. However, they suffer from a major shortcoming, as the illumination required is far from being stealthy.
    
3. **Infrared-based Attacks**: These attacks exploit the fact that CMOS sensors are often sensitive to near-infrared (NIR) light, which is invisible to the human eye, making them particularly stealthy and dangerous. While infrared projectors can introduce inconspicuous, pixel-wise modifications, they are costly and require investments of tens of thousands of USDs. On the other hand, infrared lasers are a more cost-effective alternative, but they come at the cost of precision. They can cause disruptions of service but cannot mount sophisticated, targeted attacks.

### Our Contributions

Our work bridges the gap between powerful projector-based and infrared-based attacks, while reducing the overall cost of the setup significantly. We provide a more practical and robust method for mounting inconspicuous adversarial attacks in the physical world by using infrared light along with an effective defense mechanism.

#### Novel Attack Method

We propose a new approach to generate adversarial infrared perturbations that can mount both targeted and untargeted attacks in the physical world. Our method significantly reduces the complexity of the underlying optimization problem, making it more efficient and cost-effective compared to existing solutions. Overall, it  incurs an equipment cost of less than US$50 and can be deployed in just tens of seconds. 

Our attack leverages the difference in sensitivity to NIR light between CMOS sensors and the human eye without leaving a visible trace. CMOS sensors, which are widely used in digital cameras, are often sensitive to wavelengths up to about 1100 nm, which is well into the NIR region. The human eye, on the other hand, is not sensitive to NIR light. Hence, NIR light is visible to CMOS sensor, but invisible to the human eye.

#### Real-World Robustness

We account for the spectral shift into the infrared domain, ensuring the perturbations are effective despite the limitations of the infrared spectrum. We incorporate Expectation Over Transformation (EOT) to adapt to various real-world limitations, such as brightness changes, perturbation misalignment, and spatial transformations. Our experiments demonstrate high attack success rates in various challenging conditions, including varying lighting, distances, angles, and moving vehicles (up to 30 km/h).

#### Novel Segmentation-Based Defense

Our defense builds on the observation that our perturbations introduce an abnormal number of additional shapes and edges into the image, far exceeding what is typically found in common traffic signs. We utilize the Segment Anything Model (SAM) with the ViT-L architecture to compute segmentation masks and detect shapes within an image. The defense measures the number of detected shapes and compares it to an empirically derived threshold to identify adversarial images. Our defense achieves an F1-score of up to 99% in thwarting infrared perturbation attacks, providing a robust line of defense against such adversarial inputs. The code for the defense can be found in our GitHub repository.

## Responsible Disclosure

On July 17, 2025, we responsibly disclosed our findings to Mercedes, Mobileye, Tesla, Sony, and OnSemi and suggested countermeasures, e.g., using our segmentation-based defense. We will keep this website updated with any vendor responses.

## Authors

You can find full details on our study about the susceptibility of traffic sign recognition systems to infrared perturbations in our NDSS 2026 paper, which is available [here](https://arxiv.org/pdf/2509.02042).

[Pascal Zimmer](https://informatik.rub.de/infsec/people/zimmer/)\
[Simon Lachnit](https://informatik.rub.de/infsec/people/lachnit/)\
Alexander Jan Zielinski\
[Ghassan Karame](https://ghassankarame.com/?i=1)
