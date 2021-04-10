# An End-to-End 3D ConvLSTM-based Framework for Early Diagnosis of Alzheimer's Disease from Full-Resolution Whole-Brain sMRI Scans

This repository contains the source code of the framework presented in the paper

>Selene Tomassini, Nicola Falcionelli, Paolo Sernani, Henning Müller and Aldo Franco Dragoni, *An End-to-End 3D ConvLSTM-based Framework for Early Diagnosis of Alzheimer's Disease from Full-Resolution Whole-Brain sMRI Scans*.

which aims to early detect Alzheimer's Disease (AD) from full-resolution whole-brain structural Magnetic Resonance Imaging (sMRI) scans in an end-to-end way.
The paper has been accepted for the publication at the “34th IEEE CBMS International Symposium on Computer-Based Medical Systems” (IEEE CBMS 2021).
The experiments were run on Google Colab, using the  GPU  hardware  acceleration  and  high  RAM setups. The classification is performed with a 6-layer neural network, whose backbone is a bidirectional 3D Convolutional Long Short-Term Memory (ConvLSTM) layer. 

# Data

_Merged_dataset/Dataset_ contains the NIFTI files after brain extraction and registration, divided in AD and Cognitively Normal (CN). 
Such processed data belong to:
- ADNI 1-Screening from Alzheimer’s  Disease  Neuroimaging Initiative* (ADNI, <http://adni.loni.usc.edu/>)
- OASIS-3 from Open  Access  Series  of  Imaging  Studies  (OASIS, <https://www.oasis-brains.org/>) [1]

*The investigators within the ADNI contributed to the design and implementation of ADNI and/or provided data but did not participate in analysis or writing of this study. A complete listing of ADNI investigators can be found at <http://adni.loni.usc.edu/wp-content/uploads/how_to_apply/ADNI_Acknowledgement_List.pdf>.

To download the original samples and replicate the framework from the beginning, subject's IDs involved in this study are listed in _ADNI1S_subjID.txt_ and _OASIS3_subjID.txt_ in the folder named _Subj_IDs_. 

# The proposed framework in bullet points

- Brain extraction using the Brain Extraction Tool (BET) of the FMRIB Software Library (https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSL) 
- Registration to make data coming from OASIS-3 and ADNI 1-Screening dimentionally uniform
- Merge in a unique dataset
- Re-sampling and input normalization
- Labels assignment
- Data division with a ratio of 6:2:2
- Model design
- Model training, validation and testing
- Performance evaluation

# Scripts

- _OASIS3+ADNI1S_ADvsCN.ipynb_ performs data re-sampling, input normalization, labels assignment, data division, model training and validation
- _https://drive.google.com/file/d/1ke9LtG9S_Q-MpCeTe3WNtTR_mEQndJ1h/view?usp=sharing_ is the model with the lowest validation loss across the runs
- _OASIS3+ADNI1S_ADvsCN_metrics.ipynb_ evaluates the classification metrics (accuracy, precision, specificity, sensitivity, f1-score) for the model _https://drive.google.com/file/d/1ke9LtG9S_Q-MpCeTe3WNtTR_mEQndJ1h/view?usp=sharing_ on test data
- _OASIS3+ADNI1S_ADvsCN_ROC+AUC.ipynb_ evaluates the Receiver Operating Characteristic (ROC) curve and the respective Area Under the Curve (AUC) for the model _https://drive.google.com/file/d/1ke9LtG9S_Q-MpCeTe3WNtTR_mEQndJ1h/view?usp=sharing_ on test data

# Acknowledgment

For sMRI scans belonging to ADNI, data collection and sharing was funded by ADNI (National Institutes of Health Grant U01 AG024904) and DOD ADNI (Department of Defense award number W81XWH-12-2-0012). ADNI is funded by the National Institute on Aging, the National Institute of Biomedical Imaging and Bioengineering, and through generous contributions from the following: AbbVie, Alzheimer’s Association; Alzheimer’s Drug Discovery Foundation; Araclon Biotech; BioClinica, Inc.; Biogen; Bristol-Myers Squibb Company; CereSpir, Inc.; Cogstate; Eisai Inc.; Elan Pharmaceuticals, Inc.; Eli Lilly and Company; EuroImmun; F. Hoffmann-La Roche Ltd and its affiliated company Genentech, Inc.; Fujirebio; GE Healthcare; IXICO Ltd.; Janssen Alzheimer Immunotherapy Research & Development, LLC.; Johnson & Johnson Pharmaceutical Research & Development LLC.; Lumosity; Lundbeck; Merck & Co., Inc.; Meso Scale Diagnostics, LLC.; NeuroRx Research; Neurotrack Technologies; Novartis Pharmaceuticals Corporation; Pfizer Inc.; Piramal Imaging; Servier; Takeda Pharmaceutical Company; and Transition Therapeutics. The Canadian Institutes of Health Research is providing funds to support ADNI clinical sites in Canada. Private sector contributions are facilitated by the Foundation for the National Institutes of Health (www.fnih.org). The grantee organization is the Northern California Institute for Research and Education, and the study is coordinated by the Alzheimer’s Therapeutic Research Institute at the University of Southern California. ADNI data are disseminated by the Laboratory for Neuro Imaging at the University of Southern California. 

# Reference

[1] P. J. LaMontagne, T. L. Benzinger, J. C. Morris, S. Keefe, R. Hornbeck, C. Xiong, E. Grant, J. Hassenstab,  K. Moulder, A. Vlassenkoet al., “OASIS-3:  Longitudinal  neuroimaging,  clinical,  and  cognitive  datasetfor normal aging and Alzheimer disease”, MedRxiv, 2019, https://doi.org/10.1101/2019.12.13.19014902.

# Citations

Please, cite this study** and the original databases to which such sMRI scans belong.

**The link will be provided as soon as the paper is available online.
