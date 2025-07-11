# DistalRTA
DistalRTA VUS homology modelling results

Distal renal tubular acidosis (dRTA) is a condition where the kidneys fail to properly excrete acid into the urine, leading to a buildup of acid in the blood (acidosis). This condition primarily affects the distal part of the kidney tubules, where the final acidification of urine occurs. 


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

## 🧪 Results

### Missense3D Predicts Structural Damage for Select Variants

We evaluated thirteen non-synonymous variants of uncertain significance (VUS) using the **Missense3D** tool to predict their potential impact on protein structure.  
The VUS analyzed were:

- ATP6V0A4_p.Ser544Leu  
- ATP6V1B1_p.Arg114Gln  
- ATP6V1B1_p.Leu51Arg  
- AVPR2_p.Arg248His  
- CASR_p.Ser713Asn  
- CLCN7_p.Asp603Tyr  
- DLL1_p.Thr203Ala  
- INVS_p.Ala763Thr  
- PHEX_p.Ala15Thr  
- SLC4A1_p.Asp902Val  
- SLC34A1_p.Leu519Arg  
- TMEM67_p.Leu437Phe  
- TRIM8_p.Pro543Gln  

Full Missense3D output results are provided in *Supplementary Table S1*.

---

### Variants Predicted to Cause Structural Damage

Among these, two variants were predicted to cause structural damage:

1. **ATP6V0A4_p.Ser544Leu**  
   - Missense3D detected:
     - A significant increase in steric clashes:  
       🧱 *Clash score increased from 16.50 (wild-type) to 39.84 (mutant)*
     - Disruption of buried hydrogen bonds:  
       🔗 *Serine had a relative solvent accessibility (RSA) of 1.5% and was involved in stabilizing interactions that were lost upon mutation to leucine*

   - 🔬 **Conclusion**: This suggests possible interference with protein folding or stability, potentially impairing function.

2. **INVS_p.Ala763Thr**  
   - Increased steric clashes observed:  
     🧱 *Wild-type clash score: 24.24 → Mutant: 59.17*
   - 🔬 **Conclusion**: Threonine may be poorly accommodated within the local structure.

---

### Variants Tolerated Structurally

For the remaining nine VUS, Missense3D did **not** predict significant structural damage under default criteria, suggesting these may be structurally tolerated.

---

### DynaMut Analysis for Stability Impact

To further assess the impact of structurally disruptive variants, we performed **DynaMut** analysis:

- Quantified protein stability changes using **ΔΔG values**
- Visualized structural models highlight:
  - 💡 Changes in flexibility
  - ⚡ Changes in interaction energetics

These support the predictions made by Missense3D and help prioritize variants for **experimental validation** based on structural and thermodynamic effects.


## References

- Ittisoponpisan S et al. 2019. Can Predicted Protein 3D Structures Provide Reliable Insights into whether Missense Variants Are Disease Associated? *J. Mol. Biol.* **431**:2197–2212. doi: [10.1016/J.JMB.2019.04.009](https://doi.org/10.1016/J.JMB.2019.04.009)

- Jumper J et al. 2021. Highly accurate protein structure prediction with AlphaFold. *Nature.* **596**:583–589. doi: [10.1038/S41586-021-03819-2](https://doi.org/10.1038/S41586-021-03819-2)

- Rodrigues CH et al. 2018. DynaMut: predicting the impact of mutations on protein conformation, flexibility and stability. *Nucleic Acids Res.* **46**:W350–W355. doi: [10.1093/NAR/GKY300](https://doi.org/10.1093/NAR/GKY300)
