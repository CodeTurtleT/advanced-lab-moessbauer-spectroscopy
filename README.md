# Advanced Lab: Mössbauer Spectroscopy ⚛️

## About the Project
This repository contains the Python-based data analysis pipeline for $^{57}\text{Fe}$ Mössbauer spectroscopy, conducted as part of the Advanced Physics Lab at Friedrich Schiller University Jena.

The project utilizes the quantum mechanical fitting framework **Nuclear NEXUS** developed at DESY to model hyperfine interactions, calibrate the drive system velocity scales, and resolve multi-phase structures in complex alloys.

The template scripts and core fit-routines were adopted from the official [DESY Nuclear NEXUS Examples](https://fs-mcp.pages.desy.de/nuclear-nexus/examples/examples.html#evaluation-of-a-moessbauer-spectrum).

## Key Features & Methodology
* **Drive Mode Comparison:** Complete processing pipelines for both linear **Triangle** and harmonic **Sine** excitation signals.
* **Non-Linear Back-Transformation:** Implementations of cosine-based velocity corrections to resolve the non-linear time-at-velocity probability density of the sine drive.
* **Hyperfine Field Modeling:** Advanced multi-site quantum fits extracting isomer shifts ($\delta$), quadrupole interactions ($E_Q$), and nuclear Zeeman magnetic splitting ($B_{\text{hf}}$).

## Repository Structure
* `/data` — Raw `.ws5` multi-channel analyzer data files for the $\alpha\text{-Fe}$ reference and the stainless steel sample.
* `/notebooks` — Jupyter notebooks containing the step-by-step analysis, baseline corrections, calibration, and sample fitting pipelines.
* `/results` — Exported parameter summaries and publication-ready spectral plots.

## Tech Stack
* **Python** — Core language for the data processing pipeline.
* **Nuclear NEXUS** — Specialistic quantum mechanical framework for Mössbauer spectrum simulation and optimization.
* **NumPy** — Vectorized numerical array manipulations.
* **Matplotlib** — Scientific data visualization.

---

## Analysis & Experimental Results

### 1. Velocity Calibration ($\alpha\text{-Fe}$ Reference)
The velocity scale was calibrated using a pure, magnetic $\alpha\text{-Iron}$ foil reference. Due to its cubic body-centered (bcc) crystal structure, the electric field gradient at the nucleus vanishes ($E_Q \approx 0$), isolating a clean nuclear Zeeman sextet.

* **Triangle Signal:** Handled as a linear velocity ramp providing a flat baseline, but subject to mechanical transient vibrations at the turning points, leading to an experimental center offset of $\delta \approx +0.1477 \text{ mm/s}$.
* **Sine Signal:** Modeled with a harmonic drive that completely mitigates mechanical shock but introduces a parabolic baseline. After mathematical back-transformation, the zentrierung zips down precisely close to the origin ($\delta \approx -0.0094 \text{ mm/s}$), with minor deviations attributed to the Second Doppler (thermal) Effect.

### 2. Sample Analysis (Stainless Steel / Edelstahl)
The target absorber consisted of a high-alloy stainless steel foil. Quantitative analysis using a two-site unmagnetic model in `NEXUS` successfully decoupled the overlapping features into two distinct metallurgical phases:

* **Site 1 — Ferromagnetic Phase ($\approx 18\%$ relative area):** Characterized by a significantly reduced internal magnetic hyperfine field of $B_{\text{hf}} \approx 20.94 \text{ T}$ and an isomer shift of $\delta \approx 0 \text{ mm/s}$. This confirms the presence of strain-induced martensite or ferritic clusters within the sample matrix.
* **Site 2 — Paramagnetischer Hauptanteil ($\approx 82\%$ relative area):** The dominant face-centered cubic (fcc) austenite phase. Lacking a macroscopic magnetic field ($B_{\text{hf}} = 0 \text{ T}$), the local symmetry breaking caused by the statistical neighborhood of alloy elements (Cr, Ni) induces a distinct electric quadrupole splitting of $E_Q \approx 0.29 \text{ mm/s}$, with an isomer shift of $\delta \approx 0.111 \text{ mm/s}$ relative to the source.

Additionally, the average experimental line width was found to be $\Gamma \approx 0.606 \text{ mm/s}$ ($\approx 2.91 \times 10^{-8} \text{ eV}$), which represents a **6-fold broadening** compared to the natural line width ($\Gamma_{\text{nat}}$). This quantitatively demonstrates the presence of **inhomogeneous line broadening** driven by continuous statistical fluctuations in the local coordination shells of the substitution alloy.

## Experimental Team
* **Students:** Trinity Hopp & Nelly Patzschke  
* **Supervisor:** Dr. Sakshath Sadashivaiah (institute of X-ray physics)
* **Institution:** Friedrich Schiller University Jena  

## Grading / Bewertung
The final grade for this advanced lab experiment is determined by three core evaluation components:

| Evaluation Component | Description | Weight / Gewichtung | Grade / Note |
| :--- | :--- | :---: | :---: |
| **Written Test (Antestat)** | Theoretical preparation, physical foundations, and quantum mechanics of the Mössbauer effect | *TBD* | *TBD* |
| **Experimental Execution** | Lab performance, sample handling, drive mode configuration (Triangle/Sine) | *TBD* | *TBD* |
| **Lab Report & Analysis** | Data processing pipeline, NEXUS calibration quality, and physical interpretation | *TBD* | *TBD* |
| **Final Grade (Gesamtnote)** | **Weighted average of the three components above** | **100%** | ***TBD*** |
