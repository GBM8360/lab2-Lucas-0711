# Welcome to interactive k-space Explorations

**Course:** GBM8360E - Physical Principles of Advanced MRI 
**Author:** Lucas Schulze

## About This Project

Welcome to my interactive MyST book! This project is a deeper dive into the concepts we explored in Exercise 3 of Lab 1. In the previous lab, we looked at static images to understand what happens when k-space is altered. Here, the goal is to bring those concepts to life using interactive tools. 

By using Plotly to create adjustable figures, we can tweak variables on the fly and instantly see how the spatial domain (the actual MRI image) responds. This hands-on approach is designed to move beyond simply generating expected outputs, focusing instead on developing a real intuition for how k-space governs image reconstruction.

## What We'll Explore

I have set up three interactive experiments to visualize different k-space phenomena:

1. **Masking:** What happens to our image contrast and structure when we remove the low-frequency data from the center of k-space? We'll use a slider to dynamically adjust the mask size and see the impact in real-time.
2. **Downsampling:** To speed up an MRI scan, we might acquire fewer lines of data. In this section, we'll cut the k-space data in half along one direction to observe the classic aliasing (wrap-around) artifacts that result.
3. **Rotation:** Patients rarely stay perfectly still. We will simulate a scenario where the patient suddenly rotates their head by 20 degrees right in the middle of the scan (specifically during the central lines) to see how motion corrupts the final image.










---
title: My MyST Book
description: An interactive book built with MyST
---

:::{tip} Start here
This is a template. Replace this page, and the chapters listed in the sidebar, with
your own content.

Your first job is simply to get it **published**: use this template, enable GitHub
Pages once, and let the Action build your site. Then start writing.
:::

## About this book

**TODO:** replace this with a paragraph about what your book covers.

Built with [MyST Markdown](https://mystmd.org): Markdown for the prose, Jupyter
notebooks for the computation, one `myst.yml` for the configuration, and a GitHub
Action that rebuilds and republishes on every push.

## Why interactive?

A static figure is one parameter choice out of infinitely many, frozen at publication.
The author explored a whole parameter space; the reader gets one frame of it.

An interactive figure hands that space back. It costs almost nothing to add, and it
often explains in three seconds what a paragraph of caption cannot.

## What's here

- [](./01-getting-started.md) — how to build, publish and debug this book
- [](./02-interactive-figures.md) — the interactive figure pattern, with a worked example

Add your own pages by creating a `.md` file and listing it in the `toc` section of
`myst.yml`.
