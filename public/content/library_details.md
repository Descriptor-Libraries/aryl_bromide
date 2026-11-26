# Library Details

## Molecule Identification
The initial library of primary alkyl bromides was selected from the Auto-QChem database developed by the Doyle Lab. The library was expanded to include commercially available structures suggested by Dr. Jules Schleinitz. This compilation produced a set of 12847 structurally diverse and synthetically tractable aryl bromides was obtained. The library is purposefully diverse and excludes very few functional groups to ensure it is applicable for a broad variety of purposes. Minimal curation was done to exclude radical structures, structures that are duplicates when considering isotopes and high molecular weight compounds ( > 480 g/mol )

## Conformational Searching & Conformer Selection

To account for the conformational flexibility of the substrates at a reasonable computational cost, each aryl bromide underwent a gas-phase conformational search using using Schrödinger MacroModel with the OPLS4 force field. All conformers within 21 kJ/mol (5.02 kcal/mol) of the global minimum were retained, excluding mirror-image duplicates.

If the ensemble contained more than 20 conformers, the set was reduced using atomic root mean square deviation (RMSD) clustering. The optimal number of clusters was determined by minimizing the Kelley penalty, and the centroids of these clusters were selected. The Kelley index helps identify the ideal number of clusters while ensuring that the selected conformers are structurally diverse.

## DFT Computations

All DFT geometry optimizations and subsequent frequency calculations (Gaussian 16, rev C.01) were performed at the B3LYP-GD3BJ/6-31G(d,p) level of theory with ultrafine integration grid and root mean square (RMS) force criterion of 3 x 10-4. All optimized geometries were verified by frequency computations as minima (checked for zero imaginary frequencies). Single point calculations at the M062X/def2-TZVP level of theory were then performed on the optimized geometry. Natural bond orbital (NBO) analysis was performed using the NBO7 program. NMR shifts were computed using the gauge-invariant atomic orbitals (GIAO) method. 

From the DFT calculations, global, atomic, and bond-level properties were collected for each conformer using an amended version of [Get Properties](https://github.com/SigmanGroup/Get_Properties). 

Atoms in the aryl bromide functional group were consistently numbered as shown below.

<div class="centered-container">
     <img src="/aryl_bromide/content/aryl_bromide_atom_numbering.png" alt="Aryl Bromides Atom Numbering" class="responsive-image">
</div>

The dynamic range of properties across the conformational ensemble of a single aryl bromide was summarized by using five condensed measures for each of the properties.

| Descriptor              | Definition                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------|
| Boltz                   | Boltzmann-weighted average of a property from all the conformers in an ensemble (T = 298.15 K)  |
| max                     | highest value of a property given by any conformer in an ensemble                               |
| min                     | lowest value of a property given by any conformer in an ensemble                                |
| low_E                   | value of a property from the lowest energy conformer in the ensemble                            |
| range                   | absolute value of the max - min property value within an ensemble                               |

An extended explanation of the computational workflow used to build the aryl bromide library, as well as details on the collected and predicted descriptors can be found in the original publication supporting information.

## Citation
**Aryl Bromides Sources:** Żurański, A. M.; Wang, J. Y.; Shields, B. J.; Doyle, A. G. Auto-QChem: An Automated Workflow for the Generation and Storage of DFT Calculations for Organic Molecules. React. Chem. Eng. 2022, 7 (6), 1276–1284. DOI: [10.1039/D2RE00030] (https://doi.org/10.1039/D2RE00030J)