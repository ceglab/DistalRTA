# DistalRTA
DistalRTA VUS homology modelling results

## Methods

For each gene harboring a variant of uncertain significance (VUS) resulting in a non-synonymous substitution, we retrieved the corresponding three-dimensional protein structure from the [AlphaFold Protein Structure Database](https://alphafold.ebi.ac.uk/) (release: March 2025).  
AlphaFold (Jumper et al. 2021) employs a deep learning-based approach to predict protein structures with high accuracy, making it suitable for evaluating structural consequences of amino acid substitutions.

The effect of each VUS on the protein structure was assessed using **Missense3D** (Ittisoponpisan et al. 2019), a computational tool that identifies structural damage resulting from single amino acid changes. For each variant, the reference structure, the position of the altered residue, and the specific substitution were provided as input. Missense3D evaluates features such as:
- Disruption of hydrogen bonds  
- Steric clashes  
- Cavity alterations  

to determine whether a variant is likely to compromise structural integrity.

Variants flagged by Missense3D as potentially damaging were subjected to further analysis using **DynaMut** (Rodrigues et al. 2018), which predicts changes in protein stability based on vibrational entropy and interaction energies. DynaMut uses normal mode analysis to model the conformational flexibility of both wild-type and mutant structures, providing a **ΔΔG** value to estimate the effect on protein stability.

This tiered analysis allowed for prioritization of VUS with predicted structural and thermodynamic impact for further functional investigation.

---

## References

- Ittisoponpisan S et al. 2019. Can Predicted Protein 3D Structures Provide Reliable Insights into whether Missense Variants Are Disease Associated? *J. Mol. Biol.* **431**:2197–2212. doi: [10.1016/J.JMB.2019.04.009](https://doi.org/10.1016/J.JMB.2019.04.009)

- Jumper J et al. 2021. Highly accurate protein structure prediction with AlphaFold. *Nature.* **596**:583–589. doi: [10.1038/S41586-021-03819-2](https://doi.org/10.1038/S41586-021-03819-2)

- Rodrigues CH et al. 2018. DynaMut: predicting the impact of mutations on protein conformation, flexibility and stability. *Nucleic Acids Res.* **46**:W350–W355. doi: [10.1093/NAR/GKY300](https://doi.org/10.1093/NAR/GKY300)
