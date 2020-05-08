# Deep_Learning_Peptide_MHC_Binding_Affinity_Prediction
This Project uses the pretrained full SSA model as well as other sequence embedding code from sec_str.py from Bepler et al., 2019.
GitHub link available at: https://github.com/tbepler/protein-sequence-embedding-iclr2019

This project also follows the network architecture style of MHCSeqNet (Phloyphisut et al., 2019) and uses peptide sequence, MHC allele sequence, and binding affinity sequence data from Phloyphisut et al.
GitHub link available at: https://github.com/cmb-chula/MHCSeqNet

Our model predicts peptide-MHC allele binding probabilities using structurally-aware embeddings of peptide and allele amino acid sequences

The architectural overview is as follows:
1) A structurally-aware embedding is created for both peptide and MHC alleles using the pretrained full SSA model from Bepler et al., 2019
2) Each embedding tensor (batch_size x maximum_sequence_length x embedding) is fed into a bi-directional GRU which creates a hidden vector representation for both peptides and MHC alleles
3) The hidden representations of peptide and MHC allele seqeunces are concatenated and fed through 3 feedforward layers to output the final binding probability of peptide to MHC allele

Our trained model is applied to peptides sequenced from 14 proteins in the novel coronavirus (SARS-CoV-2).

Files that are too big to store in GitHub - peptide_full_data2.pt, alpha_140_179_full_data2.pt, and alpha_50_84_full_data2.pt - can be accessed in the Google Drive at https://drive.google.com/drive/folders/1YsUF74RZjhjf8w7ntydEQ6jDBkD-45Ou?usp=sharing. They are in the data_tensors folder of protein-sequence-embedding-iclr2019-master. 
