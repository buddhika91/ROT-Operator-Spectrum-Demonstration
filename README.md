# ROT Operator Spectrum Demonstration

This repository contains a **numerical demonstration** of how the Hermitian operator defined in **Recursive Observation Theory (ROT)** produces an eigenvalue spectrum aligned with the nontrivial zeros of the Riemann zeta function on the critical line.

---

## 🔬 Background

In ROT, the fundamental Hermitian operator is

\[
\hat H_{\text{ROT}} = -i\,t\,\frac{d}{dt}.
\]

By changing variables \(x = \ln t\), this maps unitarily to the standard self-adjoint operator

\[
\hat H = -i \frac{d}{dx},
\]

whose eigenfunctions are plane waves \(e^{i \omega x}\) with **real eigenvalues** \(\omega\).

To probe the spectrum, we compute the **prime-weighted response function**

\[
F(\omega) = \sum_{n \leq N} \Lambda(n)\, n^{-1/2 - i\omega},
\]

where \(\Lambda(n)\) is the von Mangoldt function. This is known to approximate

\[
F(\omega) \;\approx\; -\frac{\zeta'(1/2+i\omega)}{\zeta(1/2+i\omega)}.
\]

Because \(\zeta'/\zeta\) has poles at the nontrivial zeros, the magnitude \(|F(\omega)|\) exhibits sharp peaks precisely at those ordinates.

---

## 📂 Repository Contents

- **`rot_hp_operator_spectrum.py`**  
  Main Python script to compute and plot the spectral response.

- **Example outputs (when run locally):**  
  - `*_spectrum.csv` – full values of \(\omega, \Re F, \Im F, |F|\).  
  - `*_peaks.csv` – detected spectral peaks.  
  - `*_match.csv` – comparison between detected peaks and known zeta zeros.  
  - `*_spectrum.png` – plot of \(|F(\omega)|\) with zeros overlaid.

---

## ▶️ Usage

Run the script with default settings:

```bash
python rot_hp_operator_spectrum.py
