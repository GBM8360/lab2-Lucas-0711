# Welcome to interactive k-space Explorations

**Course:** GBM8360E - Physical Principles of Advanced MRI <br>
**Author:** Lucas Schulze

## About This Project

Welcome to my interactive MyST book! This project is a deeper dive into the concepts we explored in Exercise 3 of Lab 1. In the previous lab, we looked at static images to understand what happens when k-space is altered. Here, the goal is to bring those concepts to life using interactive tools. 

By using Plotly to create adjustable figures, we can tweak variables on the fly and instantly see how the spatial domain (the actual MRI image) responds. This hands-on approach is designed to move beyond simply generating expected outputs, focusing instead on developing a real intuition for how k-space governs image reconstruction.

## What We'll Explore

I have set up three interactive experiments to visualize different k-space phenomena:

1. **Central and Peripheral Masking:** We apply high-pass and low-pass filters by selectively masking k-space, demonstrating how low frequencies govern global tissue contrast while high frequencies define sharp structural edges.
2. **Downsampling and Zero-Filling:** We simulate accelerated data acquisitions by skipping phase-encoding lines, comparing the aliasing (wrap-around) artifacts of true downsampling to the truncation (blurring) effects of zero-filling.
3. **Simulation of Patient Moving:** We replicate sudden head rotations and lateral translations mid-scan, exploring the severe ghosting artifacts they produce and the underlying phase inconsistencies that cause them.


(artifact-table)=
## Summary of MRI Artifacts

| Experiment | k-Space Manipulation | Image Space Effect (Artifact) |
| :--- | :--- | :--- |
| **Masking** | High/Low frequency removal | Contrast loss or blurring |
| **Downsampling** | Reduced matrix size | Aliasing (Wrap-around) |
| **Zero-Filling** | Missing lines, original size | Truncation (Resolution loss) |
| **Motion** | Spliced phase inconsistencies| Ghosting and smearing |

