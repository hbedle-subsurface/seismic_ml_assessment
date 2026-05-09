# Seismic Multi-Attribute ML Uncertainty Assessment

**Developed by [Dr. Heather Bedle](mailto:hbedle@ou.edu)**  
AASPI (Attribute Assisted Seismic Processing & Interpretation)  
University of Oklahoma, School of Geosciences  
[aaspi.ou.edu](https://www.ou.edu/mcee/labs/aaspi)

**[Launch the tool](https://hbedle-subsurface.github.io/seismic_ml_assessment/)**

---
**This is Version 1.0 in active testing. Please email hbedle@ou.edu with any questions that felt unclear, options that didn't fit your situation, or steps your workflow includes that the tool didn't ask about - THANKS!**

---

## The short version

Machine learning for seismic interpretation is powerful. It is also statistics, not magic.

This tool is a structured uncertainty assessment for geoscientists who use multi-attribute seismic ML - k-means, PCA, ICA, SOM, GMM, GTM, and related methods - as part of their interpretation workflow. It asks the questions you should be asking at every stage of the workflow, from raw seismic quality through attribute preparation, method parameterization, and geologic validation.

At the end you get two uncertainty matrices and a prioritized list of specific actions to improve your result.

---

## Why this exists

When a software platform produces a seismic facies map using machine learning, there is a very human temptation to look at the output and move on. The colors are convincing. The patterns look like geology. The software is from a reputable vendor...

But many folks forget that the algorithm found exactly what you gave it. If you gave it acquisition footprint, it clustered your footprint. If you gave it unnormalized attributes, the result reflects data scaling, not geology. If you skipped despiking, one bad trace pulled a cluster center somewhere it should not be. If you ran it on a full 3D volume when you cared about a 50ms reservoir window, the method spent most of its effort telling the water column from the basement.

None of these are ML problems. They are workflow problems. And they are extremely common - in student work, in industry practice, and in published research.

This tool is designed to surface those issues before they become decisions!

---

## What it covers

The assessment has 7 sections:

1. **Project context** - method type, geologic goal, data setting, decision stakes
2. **Seismic data quality** - dimensionality, migration quality, S/N, acquisition footprint, bandwidth, amplitude preservation, polarity, spectral balancing, vintage consistency
3. **Attribute selection & preparation** - rationale, count, type diversity, redundancy, cyclical attribute transforms, normalization, despiking, geologic sensitivity
4. **Dimension reduction** *(shown only if PCA or ICA was used)* - purpose, PCA vs ICA distinction, component evaluation, footprint in components, component selection, ICA unmixing
5. **Unsupervised classification** - data windowing, geologic hypothesis, method understanding, number of classes, initialization stability, parameter sensitivity, GMM covariance, geologic calibration
6. **Explainability** - attribute influence, spatial consistency, sensitivity testing, interpretability
7. **Geologic validation** - artifact check, depositional model consistency, known feature calibration, analog comparison, parameter stability, well calibration, uncertainty communication

**Methods covered:** k-means, PCA, ICA, GMM, SOM, GTM, and other unsupervised classification methods.

Supervised methods (PNN, SAM, CNN) will be added in a future version.

---

## Who it is for

- **Geoscientists in industry** who use ML-enabled interpretation software and want a structured way to evaluate their results before presenting them
- **Researchers** who want a framework for critically evaluating ML-based seismic interpretations - their own or others'
- **Anyone** who has ever run a seismic ML workflow and thought "this looks great" without being quite sure why

No ML expertise is required. Every question is written in plain geoscience language. You do not need to know what a covariance matrix is to use this tool - though you might know by the end of it :)

---

## How to use it

Visit the link above. The tool runs entirely in your browser - nothing is stored or transmitted anywhere. Your answers stay on your machine, and you can save a pdf at the end.

Work through the sections. Answer honestly. "I don't know" is a valid answer and scores as the highest uncertainty level - not as a punishment, but because not knowing is a real source of uncertainty in your analysis.

At the end you receive:
- **Two 2x2 uncertainty matrices** - one for data and attribute quality, one for method rigor and geologic validation
- **Section-by-section summary cards**
- **A prioritized list of specific actions** to address the gaps the assessment found

The whole thing takes about 15-20 minutes.  

---

## AASPI connection

This tool was built alongside the AASPI software suite developed at the University of Oklahoma. Many questions reference specific AASPI programs - kmeans3d, pca3d, ica3d, som3d, gmm3d, gtm3d, analyze_input, attribute_selection, and others - in dedicated AASPI note boxes throughout the questionnaire.

The tool is designed to be useful regardless of what software you are using. The AASPI notes are bonus context for students and practitioners already working within the AASPI environment.

More information about AASPI and its software tools (and if you want to try it!): [aaspi.ou.edu](https://www.ou.edu/mcee/labs/aaspi)

---

## This is a living document

Version 1.0 covers unsupervised methods and dimension reduction. Planned additions include:

- Supervised classification methods (PNN, RFC, CNN)
- SAM (Segment Anything Model) for seismic facies
- SHAP-based explainability for unsupervised workflows
- Additional geologic settings and play types

If you have used this tool and found a question that doesn't fit your workflow, a failure mode it doesn't cover, or have suggestions for what to add - please get in touch. Feedback from practitioners and students is how this tool gets better.

**Contact:** [hbedle@ou.edu](mailto:hbedle@ou.edu)  
Feedback, suggestions, and stories all welcome.

---

## Citation

If you use this tool in research, teaching, or a publication, please cite it as:

> Bedle, H. (2025). *Seismic Multi-Attribute ML Uncertainty Assessment Tool*, v1.0., 2026, AASPI, University of Oklahoma. https://hbedle-subsurface.github.io/seismic-ml-assessment/

---

## License

This work is licensed under [Creative Commons Attribution ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

You are free to share and adapt this tool provided you give appropriate credit and distribute any adaptations under the same license.

---

## Acknowledgments

Developed at the Attribute Assisted Seismic Processing & Interpretation (AASPI), University of Oklahoma, School of Geosciences.  
Built with input from AASPI students and the broader seismic interpretation community.
