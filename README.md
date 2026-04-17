# Limits of Recovering Lattice Disorder from Diffraction

This project explores how much structural disorder can be recovered from diffraction patterns.

We simulate a 2D lattice with two types of disorder:
- positional jitter (σ): random displacement of lattice points  
- vacancy (v): random removal of lattice points  

Using both classical and deep learning models, we attempt to reconstruct these parameters from diffraction images and study the limits of this inverse problem.

---

## Key Idea

Even with strong models (e.g., CNNs), some configurations of disorder produce indistinguishable diffraction patterns.

> The limitation is not only in the model — it is in the inverse mapping itself.

---

## Project Structure

- `01_diffraction_exploration.ipynb`  
  Visualizes diffraction patterns under increasing jitter and vacancy independently

- `02_diffraction_estimation_jitter.ipynb`  
  Regression task for estimating positional jitter (σ) from diffraction

- `03_diffraction_estimation_jitter_vacancy.ipynb`  
  Joint regression and classification for σ and v (Random Forest and CNN)

- `data/`  
  (Optional) Saved datasets or intermediate arrays

- `figures/` or `outputs/`  
  Generated plots (diffraction patterns, regression results, confusion matrices)

---

## Methods

- **Simulation**
  - 2D square lattice generation
  - Controlled injection of jitter and vacancy
  - Diffraction via 2D Fourier transform (magnitude only)

- **Models**
  - Random Forest (baseline)
  - Convolutional Neural Network (CNN)

- **Tasks**
  - Regression: predict continuous σ and v
  - Classification: predict discretized disorder regimes (joint 9-class problem)

---

## Results

- Positional jitter (σ) is consistently recoverable  
- Vacancy (v) is harder to estimate and shows systematic ambiguity  
- CNN improves performance over Random Forest  
- Joint classification reveals structured ambiguity:
  - σ remains separable
  - vacancy leads to confusion within σ groups

---

## Takeaway

Different disorder configurations can produce similar diffraction patterns.

> Some inverse problems are not just difficult — they are fundamentally ambiguous.

---

## Future Directions

- Explore additional disorder types (e.g., rotation, anisotropy)
- Investigate phase-aware reconstruction
- Extend to more realistic material simulations

---

## Notes

This is a controlled synthetic study intended to isolate the behavior of the inverse problem, not a full physical simulation of real materials.

---

## Author

Suvo Ganguli
