# MCB 198: Final Project
## Design of a Convolutional Neural Network for Biochemically-Informed Classification of Protein-Ligand Interactions
### Submitted by: Ilia Gelfat

## Background and Problem Statement
Proteins are responsible for a broad range of biological functions, including catalysis of biochemical reactions, structural support, cell signaling, transport of biomolecules and many more. In principle, the amino acid sequence of a protein contains all the information required to determine its function, three-dimensional structure and affinity to various molecules. However, in practice, deducing protein properties from its sequence remains an incredibly difficult computational challenge.
One common approach to predict protein properties is utilizing sequence homology. By comparing the amino acid sequence of an unknown protein to an existing database, function and structure of various domains within the protein can be inferred. While this strategy can be extremely useful in many cases, it cannot identify or predict the chemical or functional properties of novel or unique protein domains. Another approach involves molecular dynamics simulations. This method can make predictions for arbitrary amino acid sequences, regardless of their origin, while taking into account the rich chemical information found within each amino acid. However, despite notable advances in the field(1), such simulations are extremely demanding in terms of computational resources, time and expertise. In this project, I propose and develop a new computational approach for predicting protein function from its sequence. More specifically, I will focus on determining binding of the protein to various small molecule ligands.

## Rationale and Approach
Protein interactions with small molecules can provide valuable information regarding overall function. Armed with such knowledge about an unfamiliar protein, one could infer possible substrates for enzymatic reactions, identify potential drug targets based on interactions with known drug molecules, and predict additional functions based on binding to ATP, nucleic acids, metal ions etc.
The approach proposed here involves training a neural network on an existing database of protein-ligand interactions. Upon training, the network will learn to classify a sequence of amino acids into several categories – each associated with binding a specific small-molecule ligand.
Importantly, this approach aims to take into consideration some of the chemical information found in the protein sequence, while still representing it in a compact way to facilitate computation. Therefore, each amino acid will be represented by three of its chemical properties: hydrophobicity, charge and molecular weight. These three properties are important in understanding protein structure: hydrophobic residues tend to be hidden within the protein core, while hydrophilic ones are more likely to be exposed to the solvent; charge can dictate the repulsion or attraction between residues; large, bulky amino acids can cause steric hinderance, while those will lower molecular weight confer more flexibility. They are far from the only relevant properties, but should nevertheless be a reasonable starting point for the implementation of the proposed computational strategy.

## Discussion
The results described here demonstrate the potential of a more biologically informed approach to protein sequence analysis. With additional development and a larger dataset, this method could be expanded to include a broader range of ligands, including drug molecules. Furthermore, a similar approach could be applied to other structural and functional features of proteins, such as prediction of three-dimensional folding, sequence specificity of DNA and RNA binding proteins, enzymatic reaction rates and many more. The method could be further fine-tuned to specific applications by the selection of additional relevant amino acid properties (e.g. Ramachandran angles or energies associated with hydrogen bond formation). Despite the many opportunities it presents, this method is not without its limitations. In particular, the lack of a systematic way to optimize hyperparameters and network structures renders it susceptible to suboptimal performance. It is unclear, for instance, how many convolutional layers are required to reliably detect interactions between domains or residues that are not adjacent along the protein sequence. Hopefully, as the field evolves, these challenges would become more tractable.
