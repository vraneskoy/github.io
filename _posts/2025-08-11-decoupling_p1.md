---
layout: post
title: Decoupling Pt.1
date: 2025-08-05 11:12:00-0400
description: A little something I've been looking at
tags: analysis math decoupling
categories: undergraduate-posts
related_posts: false
---

<p>I'm currently trying to learn more things about harmonic analysis, so I decided to try to get a closer feel of the field. One of the things that attracted my attention was the Bourgain–Demeter Decoupling Theorem. There are a lot of materials online by Larry Guth, explaining what decoupling is and how it is useful in fields like number theory and PDEs. I found his lectures to be quite interesting and accessible. He actually has a whole survey paper about the Bourgain–Demeter Decoupling Theorem and what problems we can solve with it, which is also quite entertaining to read.</p>

<p>Here, I'm trying to summarize what I've learned so far about decoupling in a sort of accessible way for undergraduates with some exposure to Fourier Analysis.</p>

<p>From this point on, I'm going to be using the given definition of the Fourier transform. For \(f: \mathbb{R}^n \to \mathbb{C}\),</p>

$$
\hat{f}(x) = \int_{\mathbb{R}^n} f(m) e^{-2\pi i x \cdot m} \, dm
$$

Let $$\Omega \subseteq \mathbb{R}^n$$ be a region in frequency space, which we partition into a finite collection of subregions $$\Theta$$:
$$
\Omega = \bigsqcup_{\Theta} \Theta.
$$

Suppose $$f$$ is a function whose Fourier transform $$\widehat{f}$$ is supported in $$\Omega$$. We may then decompose $$f$$ into pieces corresponding to the subregions $$\Theta$$:
$$
f = \sum_{\Theta} f_\Theta,
\qquad
f_\Theta(x) = \int_{\Theta} \widehat{f}(\omega) \, e^{2\pi i \omega \cdot x} \, d\omega.
$$

{% include figure.liquid loading="eager" path="assets/img/decoupling_1.png" class="img-fluid rounded z-depth-1" zoomable=true %}

When the frequency supports of $$f_\Theta$$ are disjoint, the $$f_\Theta$$ are orthogonal in $$L^2$$, giving the identity
$$
\|f\|_{L^2} = \left( \sum_{\Theta} \|f_\Theta\|_{L^2}^2 \right)^{1/2}.
$$

Decoupling theory asks: *what happens if we replace the $$L^2$$ norm by other $$L^p$$ norms?*

---

**Definition (Decoupling Constant)**  
Let $$\Omega = \bigsqcup_{\Theta} \Theta$$ be a finite disjoint union.  
For $$1 \leq p < \infty$$, the *decoupling constant* $$\mathcal{D}_p(\Omega)$$ is the smallest constant $$C > 0$$ such that for every $$f$$ with $$\widehat{f}$$ supported in $$\Omega$$,
$$
\|f\|_{L^p(\mathbb{R}^n)} \leq C \left( \sum_{\Theta} \|f_\Theta\|_{L^p(\mathbb{R}^n)}^2 \right)^{\frac12}.
$$

---

**Example (Parabola, $$n=2$$)**  
Let $$\Omega$$ be a $$\frac{1}{A^2}$$-neighbourhood of the parabola
$$
\omega_2 = \omega_1^2, \qquad |\omega_1| \leq 1.
$$
We partition $$\Omega$$ into $$A$$ rectangles $$\Theta$$, each of dimensions $$\frac{1}{A^2} \times \frac{1}{A}$$.  
The width $$\frac{1}{A^2}$$ reflects the curvature of the parabola, while the length $$\frac{1}{A}$$ corresponds to the arc-length scale.

{% include figure.liquid loading="eager" path="assets/img/decoupling_2.png" class="img-fluid rounded z-depth-1" zoomable=true %}

---

**Theorem (Bourgain--Demeter Decoupling Theorem)**  
For $$2 \leq p \leq 6$$,
$$
\mathcal{D}_p(A) \leq C_\varepsilon \, A^\varepsilon
$$
for every $$\varepsilon > 0$$.

\]
for every \(\varepsilon > 0\).
